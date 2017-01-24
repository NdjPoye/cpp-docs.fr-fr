---
title: "push_heap (STL/CLR) | Microsoft Docs"
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
  - "cliext::push_heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push_heap (fonction) (STL/CLR)"
ms.assetid: 184fe1d9-5f75-4c11-adbb-84b6b5c8ecd3
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# push_heap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Adds an element that is at the end of a range to an existing heap consisting of the prior elements in the range.  
  
## Syntaxe  
  
```  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## Notes  
 This function behaves the same as the STL function `push_heap`.  Pour plus d'informations, consultez [push\_heap](../Topic/push_heap.md).  
  
## Configuration requise  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)