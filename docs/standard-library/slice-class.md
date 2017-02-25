---
title: "slice, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "valarray/std::slice"
  - "std.slice"
  - "slice"
  - "std::slice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice (classe)"
ms.assetid: 00f0b03d-d657-4b81-ba53-5a9034bb2bf2
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# slice, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe utilitaire de valarray qui sert à définir des sous\-ensembles unidimensionnels d'un valarray parent.  Si un valarray est considéré comme une matrice à deux dimensions avec tous les éléments dans un tableau, le secteur extrait un vecteur dans une dimension hors du tableau à deux dimensions.  
  
## Notes  
 La classe stocke les paramètres qui caractérisent un objet de type [slice\_array](../standard-library/slice-array-class.md). Le sous\-ensemble d'un valarray est construit indirectement quand un objet de classe slice apparaît en tant qu'argument pour un objet de classe [valarray](../Topic/valarray::operator.md)**\<Type\>**.  Les valeurs stockées qui spécifient le sous\-ensemble sélectionné à partir du valarray parent sont les suivantes :  
  
-   un index de départ dans le valarray ;  
  
-   une longueur totale ou le nombre d'éléments dans le secteur ;  
  
-   une longueur ou distance entre les index d'éléments ultérieurs dans le valarray.  
  
 Si l'ensemble défini par un secteur est le sous\-ensemble d'un valarray constant, le secteur est un nouveau valarray.  Si l'ensemble défini par un secteur est le sous\-ensemble d'un valarray non constant, le secteur a une sémantique de référence par rapport au valarray d'origine.  Le mécanisme d'évaluation pour les valarrays non constants permet de gagner du temps et de la mémoire.  
  
 Les opérations sur les valarrays sont garanties uniquement si les sous\-ensembles source et de destination définis par les secteurs sont distincts et que tous les index sont valides.  
  
### Constructeurs  
  
|||  
|-|-|  
|[slice](../Topic/slice::slice.md)|Définit un sous\-ensemble d'un `valarray` qui se compose d'un nombre d'éléments à égale distance les uns des autres et qui commencent à un élément spécifié.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[size](../Topic/slice::size.md)|Recherche le nombre d'éléments dans un secteur d'un `valarray`.|  
|[start](../Topic/slice::start.md)|Recherche l'index de départ d'un secteur d'un `valarray`.|  
|[stride](../Topic/slice::stride.md)|Recherche la distance entre des éléments dans un secteur d'un `valarray`.|  
  
## Spécifications  
 **En\-tête :** \<valarray\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)