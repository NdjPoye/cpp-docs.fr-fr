---
title: "accumulate (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::accumulate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accumulate (fonction) (STL/CLR)"
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# accumulate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule la somme de tous les éléments dans une plage spécifiée incluant une valeur initiale en calculant les sommes partielles consécutives, ou calcule le résultat de résultats partiels consécutifs obtenus en utilisant une opération binaire spécifiée autre que la somme.  
  
## Syntaxe  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction numérique STL de `accumulate` Pour plus d'informations, consultez [accumulate](../Topic/accumulate.md).  
  
## Configuration requise  
 **En\-tête:** \<cliext\/numeric\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [numériques](../dotnet/numeric-stl-clr.md)