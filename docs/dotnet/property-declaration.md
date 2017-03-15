---
title: "D&#233;claration de propri&#233;t&#233; | Microsoft Docs"
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
  - "__property (mot clé)"
  - "déclarer des propriétés, C++"
  - "property (mot clé C++)"
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# D&#233;claration de propri&#233;t&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La déclaration d'une propriété dans une classe managée a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Dans la conception des Extensions managées, chaque accesseur de propriété `set` ou `get` est spécifié comme méthode indépendante.  La déclaration de chaque méthode est préfixée avec le mot clé `__property`.  Le nom de la méthode commence par `set_` ou `get_`, suivi du nom réel de la propriété \(visible par l'utilisateur\).  Donc, un `Vector` fournissant une propriété `get` de coordonnée `x` la nommerait `get_x` et l'utilisateur l'appellerait `x`.  Cette convention d'affectation de noms et la spécification séparée des méthodes reflètent réellement l'implémentation sous\-jacente de la propriété à l'exécution.  Par exemple, voici notre `Vector` avec un jeu de propriétés coordonnées :  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 Il s'ensuit une répartition des fonctionnalités associées à une propriété et l'utilisateur doit unifier de façon lexicale les commandes get et set associées.  En outre, c'est en clair.  Dans la nouvelle syntaxe, plus proche de celle de C\#, le mot clé `property` est suivi du type de la propriété et de son nom sans ornement.  Les méthodes d'accès `set` et `get` sont placées dans un bloc qui suit le nom de la propriété.  Notez que contrairement à C\#, la signature de la méthode d'accès est spécifiée.  Par exemple, voici la traduction dans la nouvelle syntaxe de l'exemple de code ci\-dessus.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 Si les méthodes d'accès de la propriété reflètent des niveaux d'accès distincts \- tel qu'un `get` `public` et un `set` `private` ou `protected`, une étiquette d'accès explicite peut être spécifiée.  Par défaut, le niveau d'accès de la propriété reflète celui du niveau d'accès englobant.  Par exemple, les deux méthodes `get` et `set` sont `public` dans la définition ci\-dessus de `Vector`.  Pour rendre la méthode `set` `protected` ou `private`, la définition serait modifiée comme suit :  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here …  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 La portée d'un mot clé d'accès dans une propriété s'étend soit jusqu'à l'accolade fermante de la propriété, soit jusqu'à la spécification d'un mot clé d'accès supplémentaire.  Elle ne s'étend pas au\-delà de la définition de la propriété, jusqu'au niveau d'accès englobant dans lequel la propriété est définie.  Dans la déclaration ci\-dessus, par exemple, `Vector::dot()` est une méthode publique.  
  
 L'écriture des propriétés set\/get pour les trois coordonnées `Vector` implique trois étapes :  
  
1.  déclarez un membre d'état privé du type approprié.  
  
2.  retournez\-le lorsque l'utilisateur souhaite obtenir sa valeur.  
  
3.  assignez\-lui la nouvelle valeur.  
  
 Dans la nouvelle syntaxe, une syntaxe de propriété abrégée existe pour automatiser ce modèle d'utilisation :  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 Un effet secondaire intéressant de la syntaxe de propriété abrégée est que, pendant que le membre state en arrière plan est automatiquement généré par le compilateur, il n'est pas accessible dans la classe, sauf à travers les accesseurs set\/get.  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [property](../windows/property-cpp-component-extensions.md)