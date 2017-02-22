---
title: "Modifications dans l&#39;ordre d&#39;initialisation des constructeurs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "constructeurs, C++"
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Modifications dans l&#39;ordre d&#39;initialisation des constructeurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'ordre d'initialisation des constructeurs de classe a changé entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
## Comparaison de l'ordre d'initialisation des constructeurs  
 Sous les Extensions managées pour C\+\+, l'initialisation des constructeurs obéissait à l'ordre suivant :  
  
1.  Le constructeur de la classe de base, s'il existe, est appelé.  
  
2.  La liste d'initialisation de la classe est évaluée.  
  
3.  Le corps de code du constructeur de classes est exécuté.  
  
 Cet ordre d'exécution suit les mêmes conventions que dans la programmation C\+\+ native.  Le nouveau langage Visual C\+\+ prescrit l'ordre d'exécution suivant pour les classes CLR :  
  
1.  La liste d'initialisation de la classe est évaluée.  
  
2.  Le constructeur de la classe de base, s'il existe, est appelé.  
  
3.  Le corps de code du constructeur de classes est exécuté.  
  
 Notez que cette modification s'applique uniquement aux classes CLR ; les classes natives [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] obéissent encore aux conventions antérieures.  Dans les deux cas, ces règles s'exécutent en cascade de bas en haut à travers la totalité de la chaîne de hiérarchie d'une classe donnée.  
  
 Considérez l'exemple de code suivant utilisant les Extensions managées pour C\+\+ :  
  
```  
__gc class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
__gc class B : public A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 D'après l'ordre d'initialisation des constructeurs prescrit ci\-dessus, nous devons voir l'ordre suivant d'exécution lorsque les nouvelles instances de classe `B` sont construites :  
  
1.  Le constructeur de la classe de base `A` est appelé.  Le membre `_n` est initialisé avec la valeur `1`.  
  
2.  La liste d'initialisation pour la classe `B` est évaluée.  Le membre `_m` est initialisé avec la valeur `1`.  
  
3.  Le corps de code de la classe `B` est exécuté.  
  
 Maintenant, considérez le même code dans la nouvelle syntaxe Visual C\+\+ :  
  
```  
ref class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
ref class B : A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 L'ordre d'exécution lorsque les nouvelles instances de la classe `B` sont construites avec la nouvelle syntaxe est le suivant :  
  
1.  La liste d'initialisation pour la classe `B` est évaluée.  Le membre `_m` est initialisé avec la valeur `0` \(`0` est la valeur non initialisée du membre de classe `_m`\).  
  
2.  Le constructeur de la classe de base `A` est appelé.  Le membre `_n` est initialisé avec la valeur `1`.  
  
3.  Le corps de code de la classe `B` est exécuté.  
  
 Notez qu'une syntaxe semblable produit des résultats différents pour ces exemples de code.  Le constructeur de la classe `B` dépend de la valeur de la classe de base `A` pour initialiser son membre.  Toutefois, le constructeur de la classe `A` n'a pas encore été appelé.  Une telle dépendance peut être particulièrement dangereuse lorsque la classe héritée dépend de la mémoire ou d'une allocation de ressources pour se produire dans le constructeur de la classe de base.  
  
## Ce que signifie le passage d'Extensions managées pour C\+\+ à Visual C\+\+ 2010  
 Dans de nombreux cas, les modifications apportées à l'ordre d'exécution des constructeurs de classe doivent être transparentes pour le programmeur parce que les classes de base n'ont aucune notion du comportement des classes héritées.  Cependant, comme ces exemples de code l'illustrent, les constructeurs des classes héritées peuvent être grandement affectés lorsque leurs listes d'initialisation dépendent des valeurs des membres de la classe de base.  Lorsque vous transférez votre code des Extensions managées pour C\+\+ vers la nouvelle syntaxe, pensez à déplacer de telles constructions vers le corps du constructeur de classe, où l'exécution est garantie se produire à la fin.  
  
## Voir aussi  
 [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Constructeurs](../cpp/constructors-cpp.md)   
 [Initialiseurs de constructeur](../misc/constructor-initializers.md)