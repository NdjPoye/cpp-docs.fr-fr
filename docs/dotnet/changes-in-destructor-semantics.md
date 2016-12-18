---
title: "Modifications de la s&#233;mantique du destructeur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "destructeurs, C++"
  - "finaliseurs (C++)"
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifications de la s&#233;mantique du destructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La sémantique des destructeurs de classe a été considérablement modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 En Extensions managées, un destructeur de classe était autorisé dans une classe de référence, mais pas dans une classe value.  Cela reste inchangé dans la nouvelle syntaxe.  Toutefois, la sémantique du destructeur de classe a été modifiée.  Cette rubrique se concentre sur les raisons de cette modification et explique comment elle affecte la traduction du code CLR existant.  Il s'agit probablement de la modification la plus importante au niveau du programmeur apportée entre les deux versions du langage.  
  
## Finalisation non déterministe  
 Avant que la mémoire associée à un objet ne soit récupérée par le garbage collector, une méthode associée `Finalize` est appelée, à condition que cette dernière soit présente.  Vous pouvez imaginer cette méthode comme une sorte de super\-destructeur, car elle n'est pas liée à la durée de vie de l'objet dans le programme.  Nous appelons cela finalisation.  On ne peut pas définir le moment précis où une méthode `Finalize` sera appelée, ni même si elle le sera.  C'est ce que nous entendons lorsque nous disons que l'opération de garbage collection expose une finalisation non déterministe.  
  
 La finalisation non déterministe fonctionne efficacement avec la gestion dynamique de la mémoire.  Lorsque la mémoire disponible devient rare, le garbage collector entre en action.  Dans un environnement récupéré par le garbage collector, les destructeurs chargés de libérer de la mémoire sont inutiles.  En revanche, la finalisation non déterministe ne fonctionne pas bien si un objet conserve une ressource critique, telle qu'une connexion de base de données ou un verrouillage quelconque.  Dans ce cas, il faut libérer cette ressource au plus tôt.  Dans le monde natif, cette action est accomplie en utilisant une paire constructeur\/destructeur.  Dès que la durée de vie d'un objet prend fin, que ce soit par l'achèvement du bloc local dans lequel il est déclaré ou par le dénouement de la pile en raison de la levée d'une exception, le destructeur entre en action et la ressource est automatiquement libérée.  Cette fonctionnalité, qui manquait cruellement en Extensions managées, s'avère très efficace.  
  
 La solution fournie par le CLR consiste en l'implémentation par une classe de la méthode `Dispose` de l'interface `IDisposable`.  Le problème qui se pose alors est que `Dispose` requiert un appel explicite par l'utilisateur.  Cette solution constitue un risque d'erreur.  Le langage C\# fournit une forme relative d'automatisation par le biais d'une instruction `using` spéciale.  La conception des Extensions managées ne fournissait aucune assistance spéciale.  
  
## Destructeurs dans les Extensions managées pour C\+\+  
 Dans les Extensions managées, le destructeur d'une classe de référence est implémenté via les deux étapes suivantes :  
  
1.  Le destructeur fourni par l'utilisateur est renommé en interne en `Finalize`.  Si la classe possède une classe de base \(pour mémoire, sous le modèle objet CLR, seul l'héritage unique est pris en charge\), le compilateur injecte un appel de son finaliseur suite à l'exécution du code fourni par utilisateur.  Par exemple, considérez la hiérarchie suivante, issue de la spécification du langage des Extensions managées :  
  
```  
__gc class A {  
public:  
   ~A() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   ~B() { Console::WriteLine(S"in ~B");  }  
};  
```  
  
 Dans cet exemple, les deux destructeurs sont renommés `Finalize`.  `Finalize` de `B` se voit ajouter un appel de la méthode `Finalize` de `A` à la suite de l'appel de `WriteLine`.  Il s'agit de ce que le garbage collector appellera par défaut au cours de la finalisation.  Cette transformation interne doit se présenter de la façon suivante :  
  
```  
// internal transformation of destructor under Managed Extensions  
__gc class A {  
public:  
   void Finalize() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   void Finalize() {   
      Console::WriteLine(S"in ~B");  
      A::Finalize();   
   }  
};  
```  
  
1.  Dans la deuxième étape, le compilateur synthétise un destructeur virtuel.  Ce destructeur est ce que nos programmes utilisateur Extensions managées appellent soit directement, soit par le biais d'une application de l'expression de suppression.  Il n'est jamais appelé par le garbage collector.  
  
     Deux instructions sont placées au sein de ce destructeur synthétisé.  L'une consiste en un appel de `GC::SuppressFinalize` visant à garantir qu'il n'y aura plus d'appels de `Finalize`.  La seconde est l'appel réel de `Finalize`, qui représente le destructeur fourni par utilisateur pour cette classe.  Le résultat doit ressembler à ceci :  
  
```  
__gc class A {  
public:  
   virtual ~A() {  
      System::GC::SuppressFinalize(this);  
      A::Finalize();  
   }  
};  
  
__gc class B : public A {  
public:  
   virtual ~B() {  
      System::GC::SuppressFinalize(this);  
      B::Finalize();  
   }  
};  
```  
  
 Bien que cette implémentation permette à l'utilisateur d'appeler explicitement la méthode `Finalize` de la classe, à l'instant présent de préférence à un instant où vous n'avez pas le contrôle, elle ne correspond pas vraiment à la solution de la méthode `Dispose`.  Cela a été modifié dans [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
## Destructeurs dans la nouvelle syntaxe  
 Dans la nouvelle syntaxe, le destructeur est renommé en interne en méthode `Dispose` et la classe de référence est étendue automatiquement pour implémenter l'interface `IDispose`.  Plus précisément, sous [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], notre paire de classes est transformée comme suit :  
  
```  
// internal transformation of destructor under the new syntax  
__gc class A : IDisposable {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~A");  
   }  
};  
  
__gc class B : public A {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~B");    
      A::Dispose();   
   }  
};  
```  
  
 Si un destructeur est appelé explicitement dans la nouvelle syntaxe, ou si `delete` est appliqué à un handle de suivi, la méthode `Dispose` sous\-jacente est appelée automatiquement.  S'il s'agit d'une classe dérivée, un appel de la méthode `Dispose` de la classe de base est inséré à la fin de la méthode synthétisée.  
  
 Cependant, cela ne nous conduit pas directement à la finalisation déterministe.  Pour y parvenir, la prise en charge additionnelle d'objets de référence locaux est nécessaire. \(Il n'existe pas de prise en charge analogue en Extensions managées, ce n'est donc pas un problème de traduction.\)  
  
## Déclaration d'un objet de référence  
 [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] prend en charge la déclaration d'un objet d'une classe de référence sur la pile locale ou en tant que membre d'une classe comme s'il était directement accessible.  Ceci combiné avec l'association du destructeur et de la méthode `Dispose`, le résultat est un appel automatisé de la sémantique de finalisation sur les types référence.  
  
 Nous commencerons par définir notre classe de référence de façon à ce que la création d'objets fonctionne comme l'acquisition d'une ressource via son constructeur de classe.  Ensuite, dans le destructeur de classe, nous diffuserons la ressource acquise lorsque l'objet a été créé.  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // … everything else …  
};  
```  
  
 L'objet se déclare localement à l'aide du nom de type, mais sans le chapeau d'accompagnement.  Toutes les utilisations de l'objet, tel que l'appel d'une méthode, se font via le point de sélection de membre \(`.`\) plutôt qu'avec la flèche \(`->`\).  À la fin du bloc, le destructeur associé, transformé en `Dispose`, est automatiquement appelé, comme illustré ci\-après :  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here –  
   // that is, r.Dispose() is invoked  
}  
```  
  
 Comme avec l'instruction `using` en C\#, cela n'empêche pas la contrainte CLR selon laquelle tous les types référence doivent être alloués sur le tas CLR.  La sémantique sous\-jacente reste inchangée.  L'utilisateur aurait tout aussi bien pu écrire la formule équivalente suivante \(et c'est d'ailleurs probablement la transformation interne qu'effectue le compilateur\) :  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 Dans l'effet, dans la nouvelle syntaxe, les destructeurs sont à nouveau appariés aux constructeurs comme un mécanisme automatique d'acquisition\/libération lié à la durée de vie d'un objet local.  
  
## Déclaration d'une méthode Finalize explicite  
 Dans la nouvelle syntaxe, comme nous l'avons vu, le destructeur est synthétisé dans la méthode `Dispose`.  Cela signifie que lorsque le destructeur n'est pas appelé explicitement, le garbage collector, au cours de la finalisation, ne trouvera pas, comme il le faisait auparavant, de méthode `Finalize` associée pour l'objet.  Pour prendre en charge à la fois la destruction et la finalisation, nous avons introduit une syntaxe spéciale pour fournir un finaliseur.  Par exemple :  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 Le préfixe `!` est analogue au tilde \(`~`\), qui présente un destructeur de classe. Autrement dit, les deux méthodes de post\-durée de vie possèdent un jeton qui préfixe le nom de la classe.  Si la méthode `Finalize` synthétisée se produit dans une classe dérivée, un appel de la méthode `Finalize` de la classe de base est inséré à sa fin.  Si le destructeur est appelé explicitement, le finaliseur est supprimé.  Le résultat de la transformation doit ressembler à ceci :  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## Transfert des Extensions managées pour C\+\+ vers Visual C\+\+ 2010  
 Cela signifie que le comportement à l'exécution d'un programme Extensions managées pour C\+\+ est modifié lorsqu'il est compilé sous [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], chaque fois qu'une classe de référence contient un destructeur non trivial.  L'algorithme de traduction requis se présente ainsi :  
  
1.  Si un destructeur est présent, réécrivez\-le pour en faire le finaliseur de la classe.  
  
2.  Si une méthode `Dispose` est présente, réécrivez\-la pour en faire le destructeur de classe.  
  
3.  Si un destructeur est présent mais qu'il n'existe aucune méthode `Dispose`, conservez le destructeur en mettant en œuvre le premier élément.  
  
 En transférant votre code des Extensions managées vers la nouvelle syntaxe, vous risquez de manquer l'exécution de cette transformation.  Si l'application dépendait d'une manière ou d'une autre de l'exécution de méthodes de finalisation associées, son comportement sera silencieusement différent de celui que vous attendiez.  
  
## Voir aussi  
 [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Destructeurs et finaliseurs dans Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md)