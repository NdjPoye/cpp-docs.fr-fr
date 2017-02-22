---
title: "Interpr&#233;tation de l&#39;op&#233;rateur d&#39;indice | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), mettre en indice"
  - "interpréter les opérateurs d'indice"
  - "opérateurs (C++), interprétation de l'indice"
  - "opérateur d'indice, interprétation de"
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interpr&#233;tation de l&#39;op&#233;rateur d&#39;indice
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme d'autres opérateurs, l'opérateur d'indice \(**\[ \]**\) peut être redéfini par l'utilisateur.  Le comportement par défaut de l'opérateur d'indice, s'il n'est pas surchargé, est de combiner le nom d'un tableau et l'indice à l'aide de la méthode suivante :  
  
 \*\(\(*array\-name*\) \+ \(*subscript*\)\)  
  
 Comme dans toute addition qui implique des types pointeur, la mise à l'échelle est exécutée automatiquement pour ajuster la taille du type.  Par conséquent, la valeur résultante n'est pas les octets *subscript* provenant du début du *array\-name* ; il s'agit plutôt de l'élément *subscript* du tableau. \(Pour plus d'informations sur cette conversion, consultez [Opérateurs additifs](../cpp/additive-operators-plus-and.md).\)  
  
 De même, pour des tableaux multidimensionnels, l'adresse est dérivée à l'aide de la méthode suivante :  
  
 **\(\(**   
 ***array\-name* \) \+ \(**   
 ***subscript* 1**  *max*2 *\* max*3*...max*n\)               **\+** *subscript*2 *\* max*3*...max*n\)                    . . .  *\+* *subscript*n\)\)  
  
## Voir aussi  
 [Tableaux](../cpp/arrays-cpp.md)