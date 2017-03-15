---
title: "make_heap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::make_heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_heap (fonction) (STL/CLR)"
ms.assetid: bc1bed28-7a26-4540-901d-5584cd117ea1
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# make_heap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convertit les éléments d'une plage spécifiée en un segment de mémoire dans lequel le premier élément est le plus gros et pour lequel un critère de tri peut être spécifié avec un attribut binaire.  
  
## Syntaxe  
  
```  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `make_heap` de STL.  Pour plus d'informations, consultez [make\_heap](../Topic/make_heap.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)