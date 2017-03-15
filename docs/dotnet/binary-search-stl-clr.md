---
title: "binary_search (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::binary_search"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_search (fonction) (STL/CLR)"
ms.assetid: 520869cc-7cd3-4c81-b439-05f042474416
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# binary_search (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si un élément dans une plage triée est égal à une valeur spécifiée ou lui est équivalent d'une manière spécifiée par un prédicat binaire.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _Ty> inline  
    bool binary_search(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    bool binary_search(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `binary_search` de STL.  Pour plus d'informations, consultez [binary\_search](../Topic/binary_search.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)