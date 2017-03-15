---
title: "partial_sort_copy (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::partial_sort_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial_sort_copy (fonction) (STL/CLR)"
ms.assetid: ed4af83e-7554-4f6d-bf54-c56fa6210fe8
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# partial_sort_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Éléments de copies d'une plage source dans une plage de destination où les éléments sources sont classés par un moins qu'un attribut ou binaire spécifié différent.  
  
## Syntaxe  
  
```  
template<class _InIt, class _RanIt> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2);  
template<class _InIt, class _RanIt, class _Pr> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `partial_sort_copy` de STL.  Pour plus d'informations, consultez [partial\_sort\_copy](../Topic/partial_sort_copy.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)