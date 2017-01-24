---
title: "gslice, classe | Microsoft Docs"
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
  - "std::gslice"
  - "std.gslice"
  - "gslice"
  - "valarray/std::gslice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice (classe)"
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
caps.latest.revision: 21
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gslice, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe utilitaire de valarray qui sert à définir des sous\-ensembles multidimensionnels d'un valarray.  Si un valarray est considéré comme une matrice multidimensionnelle avec tous les éléments dans un tableau, le secteur extrait un vecteur du tableau multidimensionnel.  
  
## Notes  
 La classe stocke les paramètres qui caractérisent un objet de type [gslice\_array](../standard-library/gslice-array-class.md).  Le sous\-ensemble d'un valarray est construit indirectement quand un objet de classe gslice apparaît en tant qu'argument pour un objet de classe [valarray](../Topic/valarray::operator.md)**\<Type\>**.  Les valeurs stockées qui spécifient le sous\-ensemble sélectionné à partir du valarray parent sont les suivantes :  
  
-   un index de départ ;  
  
-   un vecteur de longueur de classe **valarray\<size\_t\>** ;  
  
-   un vecteur de stride de classe **valarray\<size\_t\>**.  
  
 Les deux vecteurs doivent avoir la même longueur.  
  
 Si l'ensemble défini par un gslice est le sous\-ensemble d'un valarray constant, le gslice est un nouveau valarray.  Si l'ensemble défini par un gslice est le sous\-ensemble d'un valarray non constant, le gslice a une sémantique de référence par rapport au valarray d'origine.  Le mécanisme d'évaluation pour les valarrays non constants permet de gagner du temps et de la mémoire.  
  
 Les opérations sur les valarrays sont garanties uniquement si les sous\-ensembles source et de destination définis par les gslices sont distincts et que tous les index sont valides.  
  
### Constructeurs  
  
|||  
|-|-|  
|[gslice](../Topic/gslice::gslice.md)|Définit un sous\-ensemble d'un `valarray` composé de plusieurs sections du `valarray` qui commencent toutes à un élément spécifié.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[size](../Topic/gslice::size.md)|Recherche les valeurs de tableau spécifiant le nombre d'éléments dans un secteur général d'un `valarray`.|  
|[démarrer](../Topic/gslice::start.md)|Recherche l'index de départ d'un secteur général d'un `valarray`.|  
|[stride](../Topic/gslice::stride.md)|Recherche la distance entre des éléments dans un secteur général d'un `valarray`.|  
  
## Spécifications  
 **En\-tête :** \<valarray\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)