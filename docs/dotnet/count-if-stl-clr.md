---
title: "count_if (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::count_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count_if (fonction) (STL/CLR)"
ms.assetid: a8aa149d-20b8-4b3f-917b-1ec66f178a5d
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# count_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne le nombre d'éléments dans une étendue dont les valeurs correspondent à une valeur spécifiée.  
  
## Syntaxe  
  
```  
template<class _InIt, class _Pr> inline  
    typename iterator_traits<_InIt>::difference_type  
        count_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `count_if` de STL.  Pour plus d'informations, consultez [count\_if](../Topic/count_if.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)