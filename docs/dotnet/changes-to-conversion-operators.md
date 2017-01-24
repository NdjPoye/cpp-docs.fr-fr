---
title: "Modifications apport&#233;es aux op&#233;rateurs de conversion | Microsoft Docs"
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
  - "opérateurs de conversion"
  - "conversions, explicites"
  - "explicit (mot clé C++)"
  - "opérateurs (C++), conversion de type explicite"
  - "conversion de types, conversions explicites"
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifications apport&#233;es aux op&#233;rateurs de conversion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe des opérateurs de conversion a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Un exemple consiste à écrire `op_Implicit` pour spécifier une conversion.  Par exemple, voici une définition de `MyDouble` extraite des spécifications du langage :  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Cette formule dit qu'étant donné un entier, l'algorithme pour convertir cet entier en `MyDouble` est fourni par l'opérateur `op_Implicit`.  De plus, cette conversion sera effectuée implicitement par le compilateur.  De même, étant donné un objet `MyDouble`, les deux opérateurs `op_Explicit` fournissent les algorithmes respectifs pour convertir cet objet en un entier ou une entité `String` managée.  Pourtant, le compilateur n'effectuera pas la conversion à moins que l'utilisateur ne le demande explicitement.  
  
 En C\#, ce cas se présente de la façon suivante :  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 Le code C\# ressemble plus à du code C\+\+ que les Extensions managées pour C\+\+.  Ce n'est pas le cas dans la nouvelle syntaxe.  
  
 La commission ISO\-C\+\+ a introduit un mot clé, `explicit`, destiné à maîtriser les conséquences involontaires – par exemple, une classe `Array` qui prend un seul argument entier comme dimension convertit implicitement tout entier en un objet `Array` qui n'est pas celui que vous souhaitez.  Une façon d'empêcher cette situation est l'idiome de conception d'un deuxième argument factice d'un constructeur.  
  
 En revanche, vous ne devez pas fournir de paire de conversion lors de la conception d'un type de classe en C\+\+.  Le meilleur exemple en est la classe de chaîne standard.  La conversion implicite est le constructeur à argument unique qui prend une chaîne de style C.  Elle ne fournit cependant pas l'opérateur de conversion implicite correspondant \(celui convertissant un objet chaîne en une chaîne de style C, mais requiert plutôt que l'utilisateur appelle une fonction nommée explicitement\) : ici, `c_str()`.  
  
 Ainsi, l'association d'un comportement implicite\/explicite sur un opérateur de conversion \(de même que l'encapsulation du jeu de conversions sous un seul format de déclaration\) semble être une amélioration par rapport à la prise en charge C\+\+ d'origine des opérateurs de conversion, qui a finalement conduit au mot clé `explicit`.  La prise en charge des opérateurs de conversion par le langage [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] se présente de la façon suivante, légèrement moins prolixe que celle de C\# en raison du comportement par défaut de l'opérateur qui prend en charge une application implicite de l'algorithme de conversion :  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Une autre modification est le fait qu'un constructeur à argument unique est traité comme s'il était déclaré comme `explicit`.  Cela signifie que pour déclencher ses appels, il faut passer par un cast explicite.  Notez toutefois que si un opérateur de conversion explicite est défini, c'est lui, et non le constructeur à argument unique, qui est appelé.  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)