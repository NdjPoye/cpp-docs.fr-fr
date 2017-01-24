---
title: "unique (STL/CLR) | Microsoft Docs"
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
  - "cliext::unique"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique (fonction) (STL/CLR)"
ms.assetid: 833cc314-b452-4659-bbb4-575c2bb63855
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unique (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Removes duplicate elements that are adjacent to each other in a specified range.  
  
## Syntaxe  
  
```  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## Notes  
 This function behaves the same as the STL function `unique`.  Pour plus d'informations, consultez [uniques](../Topic/unique%20\(%3Calgorithm%3E\).md).  
  
## Configuration requise  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)