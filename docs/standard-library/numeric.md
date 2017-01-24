---
title: "&lt; numeric &gt; | Microsoft Docs"
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
  - "std::<numeric>"
  - "std.<numeric>"
  - "<numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête de < nombre >"
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; numeric &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les fonctions de modèle de conteneur qui exécutent des algorithmes pour le traitement numérique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <numeric>  
```  
  
## <a name="remarks"></a>Remarques  
 Ces algorithmes ressemblent aux algorithmes STL, mais font partie de la bibliothèque C++ standard. Ils sont toutefois compatibles avec STL, et, comme les algorithmes STL, ils peuvent traiter diverses structures de données. Cela comprend les classes de conteneur STL, par exemple, [vecteur](vector%20Class.md) et [liste](../standard-library/list-class.md), et des structures de données défini par le programme et les tableaux d’éléments qui satisfont à la configuration requise d’un algorithme particulier. Ces algorithmes atteignent ce niveau de généralité en parcourant les éléments d'un conteneur indirectement, via des itérateurs. Les algorithmes traitent les plages d'itérateurs qui sont généralement spécifiées par leur position de début ou de fin. Les plages référencées doivent être valides, c'est-à-dire que tous les pointeurs de ces plages doivent pouvoir être déréférencés et se trouver dans les séquences de chaque plage. La dernière position doit être accessible depuis la première au moyen d'une incrémentation.  
  
 Les algorithmes étendent les actions prises en charge par les opérations et les fonctions membres de chaque conteneur STL, et permettent l'interaction avec différents types d'objets conteneurs en même temps.  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[accumuler](../Topic/%3Cnumeric%3E%20functions.md#accumulate)|Calcule la somme de tous les éléments d'une plage spécifiée (y compris une valeur initiale) en calculant des sommes partielles successives, ou calcule le résultat de résultats partiels consécutifs qui sont obtenus en utilisant une opération binaire spécifiée au lieu de l'opération de somme.|  
|[adjacent_difference](../Topic/%3Cnumeric%3E%20functions.md#adjacent_difference)|Détermine les différences successives entre chaque élément et son prédécesseur au sein d'une plage d'entrée et génère les résultats dans une plage de destination, ou calcule le résultat d'une procédure généralisée dans laquelle l'opération de différence est remplacée par une autre opération binaire spécifiée.|  
|[inner_product](../Topic/%3Cnumeric%3E%20functions.md#inner_product)|Calcule la somme du produit d'éléments de deux plages et l'ajoute à une valeur initiale spécifiée, ou calcule le résultat d'une procédure généralisée dans laquelle les opérations de somme et de produit sont remplacées par d'autres opérations binaires spécifiées.|  
|[IOTA](../Topic/%3Cnumeric%3E%20functions.md#iota)|Stocke une valeur de départ, en commençant par le premier élément et en remplissant avec des incréments successifs de la valeur (`value++`) de chaque élément de l'intervalle `[first, last)`.|  
|[partial_sum](../Topic/%3Cnumeric%3E%20functions.md#partial_sum)|Calcule une série de sommes dans une plage d’entrée du premier élément via le *i*ième élément et stocke le résultat de chaque somme dans le *je*ième élément d’une plage de destination ou calcule le résultat d’une procédure généralisée où l’opération de somme est remplacée par une autre opération binaire spécifiée.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

