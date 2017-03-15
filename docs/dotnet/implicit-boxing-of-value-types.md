---
title: "Conversion boxing implicite de types valeur | Microsoft Docs"
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
  - "__box (mot clé)"
  - "conversion boxing"
  - "conversion boxing, __box (mot clé)"
  - "conversion boxing, Visual C++"
  - "types valeur, boxed"
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Conversion boxing implicite de types valeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La conversion boxing de types valeur a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 En termes de conception de langage, nous avons privilégié une position philosophique au détriment d'un point de vue pratique s'agissant de cette fonctionnalité. Dans la pratique, cela s'est révélé être une erreur.  Pour faire une analogie, dans la conception initiale de l'héritage multiple dans le langage, Stroustrup décidait qu'un sous\-objet de classe de base virtuelle ne pouvait pas être initialisé dans un constructeur de classe dérivée, et par conséquent le langage exigeait que toute classe utilisée comme classe de base virtuelle définisse un constructeur par défaut.  La dérivation virtuelle suivante appellerait ce constructeur par défaut.  
  
 Le problème d'une hiérarchie de classe de base virtuelle est qu'à chaque dérivation suivante, la responsabilité de l'initialisation du sous\-objet virtuel partagé se déplace.  Par exemple, si je définis une classe de base dont l'initialisation requiert l'allocation d'une mémoire tampon, la taille de celle\-ci spécifiée par l'utilisateur peut être passée en tant qu'argument au constructeur.  Si je fournis par la suite deux dérivations virtuelles, que nous appellerons `inputb` et `outputb`, chacune fournit une valeur particulière au constructeur de classe de base.  Mais lorsque j'ai dérivé une classe `in_out` à la fois d'`inputb` et d'`outputb`, aucune de ces valeurs du sous\-objet de classe de base virtuelle partagée ne peut raisonnablement être autorisée à évaluer.  
  
 Par conséquent, dans la conception originelle du langage, Stroustrup refusait l'initialisation explicite d'une classe de base virtuelle dans la liste d'initialiseurs de membre du constructeur de classe dérivée.  Bien que cela résolve le problème, l'incapacité de diriger l'initialisation de la classe de base virtuelle s'est révélée inapplicable d'un point de vue pratique.  Keith Gorlen, de l'Institut National de la Santé, qui avait implémenté une version gratuite de la bibliothèque de collection Smalltalk appelée nihcl, a puissamment argumenté pour convaincre Stroustrup qu'il devait rechercher une conception plus souple du langage.  
  
 Un principe de la conception hiérarchique orientée objet stipule qu'une classe dérivée ne devrait être concernée que par l'implémentation non privée de ses classes de base immédiates.  Pour pouvoir prendre en charge une conception d'initialisation souple de l'héritage virtuel, Stroustrup a été contraint de violer ce principe.  La classe la plus dérivée dans une hiérarchie assume la responsabilité de l'initialisation de tous les sous\-objets virtuels, où qu'elle se situe dans la hiérarchie.  Par exemple, `inputb` et `outputb` sont toutes deux chargées d'initialiser explicitement leur classe de base virtuelle immédiate.  Lorsque `in_out` dérive de `inputb` et de `outputb`, `in_out` devient responsable de l'initialisation de la classe de base virtuelle qui auparavant était supprimée, et l'initialisation rendue explicite au sein de `inputb` et `outputb` est supprimée.  
  
 Cela apporte la souplesse nécessaire aux développeurs de langage, mais au prix d'une sémantique compliquée.  Cette complexité peut être allégée en n'autorisant pas une classe de base virtuelle à avoir un état et en lui permettant simplement de spécifier une interface.  Il s'agit de l'idiome de conception recommandé dans C\+\+.  Dans la programmation du CLR, il est élevé au rang de stratégie, s'agissant du type d'interface.  
  
 Voici un exemple de code simple – dans ce cas, la conversion boxing explicite est inutile :  
  
```  
// Managed Extensions for C++ requires explicit __box operation  
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };  
Object* myObjArray __gc[] = {   
   __box(26), __box(27), __box(28), __box(29), __box(30)  
};  
  
Console::WriteLine( "{0}\t{1}\t{2}", __box(0),  
   __box(my1DIntArray->GetLowerBound(0)),  
   __box(my1DIntArray->GetUpperBound(0)) );  
```  
  
 Comme vous pouvez le constater, il y a de nombreuses conversions boxing.  Sous [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], la conversion boxing de type valeur est implicite :  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## Voir aussi  
 [Types valeur et leurs comportements \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Boxing](../windows/boxing-cpp-component-extensions.md)