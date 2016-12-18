---
title: "&lt;valarray&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<valarray>"
  - "valarray/std::<valarray>"
  - "std::<valarray>"
  - "<valarray>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray (en-tête)"
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;valarray&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle valarray et de nombreuses fonctions et classes de modèle de prise en charge.  
  
## Syntaxe  
  
```  
  
#include <valarray>  
  
```  
  
## Notes  
 Une latitude inhabituelle est accordée à ces fonctions et classes de modèle afin d'améliorer les performances.  Plus spécifiquement, toute fonction qui retourne le type **valarray\<**T1**\>** peut retourner un objet d'un autre type T2.  Dans ce cas, une fonction qui accepte un ou plusieurs arguments de type **valarray\<**T2**\>** doit avoir des surcharges qui acceptent des combinaisons arbitraires de ces arguments, chacun remplacé par un argument de type T2.  
  
### Fonctions  
  
|||  
|-|-|  
|[abs](../Topic/abs%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à la valeur absolue des éléments du valarray d'entrée.|  
|[acos](../Topic/acos%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à l'arccosinus des éléments du valarray d'entrée.|  
|[asin](../Topic/asin%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à l'arcsinus des éléments du valarray d'entrée.|  
|[atan](../Topic/atan%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à la valeur principale de l'arctangente des éléments du valarray d'entrée.|  
|[atan2](../Topic/atan2%20\(%3Cvalarray%3E\).md)|Retourne un valarray dont les éléments sont égaux à l'arctangente des composants cartésiens spécifiés par une combinaison de constantes et d'éléments de valarrays.|  
|[cos](../Topic/cos%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux au cosinus des éléments du valarray d'entrée.|  
|[cosh](../Topic/cosh%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux au cosinus hyperbolique des éléments du valarray d'entrée.|  
|[exp](../Topic/exp%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à l'exponentiel naturel des éléments du valarray d'entrée.|  
|[log](../Topic/log%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux au logarithme naturel des éléments du valarray d'entrée.|  
|[log10](../Topic/log10%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux au logarithme commun ou en base 10 des éléments du valarray d'entrée.|  
|[pow](../Topic/pow%20\(%3Cvalarray%3E\).md)|Opère sur les éléments des constantes et valarrays d'entrée, retournant un valarray dont les éléments sont égaux à une base spécifiée soit par les éléments d'un valarray d'entrée, soit par une constante élevée à une puissance spécifiée par les éléments d'un valarray d'entrée ou une constante.|  
|[sin](../Topic/sin%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux au sinus des éléments du valarray d'entrée.|  
|[sinh](../Topic/sinh%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux au sinus hyperbolique des éléments du valarray d'entrée.|  
|[sqrt](../Topic/sqrt%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à la racine carrée des éléments du valarray d'entrée.|  
|[swap](../Topic/swap%20\(%3Cvalarray%3E\).md)||  
|[tan](../Topic/tan%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à la tangente des éléments du valarray d'entrée.|  
|[tanh](../Topic/tanh%20\(%3Cvalarray%3E\).md)|Opère sur les éléments d'un valarray d'entrée, en retournant un valarray dont les éléments sont égaux à la tangente hyperbolique des éléments du valarray d'entrée.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[\!\=, opérateur](../Topic/operator!=%20\(%3Cvalarray%3E\).md)|Teste si les éléments correspondants de deux valarrays de taille égale sont inégaux ou si tous les éléments d'un valarray sont inégaux à une valeur spécifiée du type d'élément du valarray.|  
|[operator%](../Topic/operator%25.md)|Obtient le reste de la division des éléments correspondants de deux valarrays de taille égale ou de la division d'un valarray par une valeur spécifiée du type d'élément du valarray ou de la division d'une valeur spécifiée par un valarray.|  
|[operator&](../Topic/operator&.md)|Obtient le résultat de l'opération **AND** binaire entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément.|  
|[operator&&](../Topic/operator&&.md)|Obtient le résultat de l'opération **AND** logique entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément du valarray.|  
|[operator\>](../Topic/operator%3E%20\(%3Cvalarray%3E\).md)|Teste si les éléments d'un valarray sont supérieurs aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou inférieurs à une valeur spécifiée du type d'élément du valarray.|  
|[operator\>\=](../Topic/operator%3E=%20\(%3Cvalarray%3E\).md)|Teste si les éléments d'un valarray sont supérieurs ou égaux aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou égaux à, ou inférieurs ou égaux à, une valeur spécifiée.|  
|[operator\>\>](../Topic/operator%3E%3E%20\(%3Cvalarray%3E\).md)|Décale vers la droite les bits de chaque élément d'un valarray d'un nombre spécifié de positions ou d'une quantité d'éléments spécifiée par un deuxième valarray.|  
|[operator\<](../Topic/operator%3C%20\(%3Cvalarray%3E\).md)|Teste si les éléments d'un valarray sont inférieurs aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou inférieurs à une valeur spécifiée.|  
|[operator\<\=](../Topic/operator%3C=%20\(%3Cvalarray%3E\).md)|Teste si les éléments d'un valarray sont inférieurs ou égaux aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou égaux à, ou inférieurs ou égaux à, une valeur spécifiée.|  
|[operator\<\<](../Topic/operator%3C%3C%20\(%3Cvalarray%3E\).md)|Décale vers la gauche les bits de chaque élément d'un valarray d'un nombre spécifié de positions ou d'une quantité d'éléments spécifiée par un deuxième valarray.|  
|[operator\*](../Topic/operator*%20\(%3Cvalarray%3E\).md)|Obtient le produit entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément du valarray.|  
|[operator\+](../Topic/operator+%20\(%3Cvalarray%3E\).md)|Obtient la somme des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément du valarray.|  
|[operator\-](../Topic/operator-%20\(%3Cvalarray%3E\)2.md)|Obtient la différence entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément du valarray.|  
|[operator\/](../Topic/operator-%20\(%3Cvalarray%3E\)1.md)|Obtient le quotient entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément du valarray.|  
|[operator\=\=](../Topic/operator==%20\(%3Cvalarray%3E\).md)|Teste si les éléments correspondants de deux valarrays de taille égale sont égaux ou si tous les éléments d'un valarray sont égaux à une valeur spécifiée du type d'élément du valarray.|  
|[operator^](../Topic/operator%5E.md)|Obtient le résultat de l'opération `OR` exclusif binaire entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément.|  
|[operator&#124;](../Topic/operator%7C.md)|Obtient le résultat de l'opération `OR` binaire entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément.|  
|[operator&#124;&#124;](../Topic/operator%7C%7C.md)|Obtient le résultat de l'opération `OR` logique entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément du valarray.|  
  
### Classes  
  
|||  
|-|-|  
|[gslice, classe](../standard-library/gslice-class.md)|Classe utilitaire de valarray qui sert à définir des secteurs multidimensionnels d'un valarray.|  
|[gslice\_array, classe](../standard-library/gslice-array-class.md)|Classe de modèle interne auxiliaire qui prend en charge les objets de secteurs généraux en fournissant des opérations entre des tableaux de sous\-ensembles définis par le secteur général d'un valarray.|  
|[indirect\_array, classe](../standard-library/indirect-array-class.md)|Classe de modèle interne auxiliaire qui prend en charge les objets qui sont des sous\-ensembles de valarrays en fournissant des opérations entre des tableaux de sous\-ensembles définis en spécifiant un sous\-ensemble d'index d'un valarray parent.|  
|[mask\_array, classe](../standard-library/mask-array-class.md)|Classe de modèle interne auxiliaire qui prend en charge les objets qui sont des sous\-ensembles de valarrays parents, spécifiés avec une expression booléenne, en fournissant des opérations entre les tableaux de sous\-ensembles.|  
|[slice, classe](../standard-library/slice-class.md)|Classe utilitaire de valarray qui sert à définir des sous\-ensembles vectoriels unidimensionnels d'un valarray parent.|  
|[slice\_array, classe](../standard-library/slice-array-class.md)|Classe de modèle interne auxiliaire qui prend en charge les objets de secteurs en fournissant des opérations entre des tableaux de sous\-ensembles définis par le secteur d'un valarray.|  
|[valarray, classe](../standard-library/valarray-class.md)|La classe de modèle décrit un objet qui contrôle une séquence d'éléments de type **Type** qui sont stockés sous forme de tableau et conçu pour effectuer des opérations mathématiques à grande vitesse et optimisé pour les performances de calcul.|  
  
### Spécialisations  
  
|||  
|-|-|  
|[valarray\<bool\>, classe](../standard-library/valarray-bool-class.md)|Version spécialisée de la classe de modèle valarray \<**Type**\> pour les éléments de type `bool`.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)