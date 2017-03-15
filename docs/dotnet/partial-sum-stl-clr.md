---
title: "partial_sum (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::partial_sum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial_sum (fonction) (STL/CLR)"
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# partial_sum (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Computes a series of sums in an input range from the first element through the `i`th element and stores the result of each such sum in `i`th element of a destination range or computes the result of a generalized procedure where the sum operation is replaced by another specified binary operation.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Notes  
 This function behaves the same as the STL numeric function `partial_sum`.  Pour plus d'informations, consultez [partial\_sum](../Topic/partial_sum.md).  
  
## Configuration requise  
 **Header:** \<cliext\/numeric\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [numériques](../dotnet/numeric-stl-clr.md)