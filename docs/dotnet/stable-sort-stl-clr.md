---
title: "stable_sort (STL/CLR) | Microsoft Docs"
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
  - "cliext::stable_sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stable_sort (fonction) (STL/CLR)"
ms.assetid: c28fc2df-c68b-4923-ac16-9f8edd926fbb
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stable_sort (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Organise les éléments d'une plage spécifiée dans un ordre non descendant ou selon un critère de classement spécifié par un attribut binaire et conserve l'ordre relatif des éléments équivalents.  
  
## Syntaxe  
  
```  
template<class _BidIt> inline  
    void stable_sort(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `stable_sort` de STL.  Pour plus d'informations, consultez [stable\_sort](../Topic/stable_sort.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)