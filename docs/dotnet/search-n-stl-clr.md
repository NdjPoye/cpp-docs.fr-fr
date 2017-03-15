---
title: "search_n (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::search_n"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "search_n (fonction) (STL/CLR)"
ms.assetid: 34d9fd07-b160-4b1e-a632-303200740dfc
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# search_n (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la première sous\-séquence dans une plage d'un nombre spécifié d'éléments contenant une valeur particulière ou une relation à cette valeur comme spécifié par un attribut binaire.  
  
## Syntaxe  
  
```  
template<class _FwdIt1, class _Diff2, class _Ty> inline  
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _Diff2 _Count, const _Ty& _Val);  
template<class _FwdIt1, class _Diff2, class _Ty, class _Pr> inline  
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _Diff2 _Count, const _Ty& _Val, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `search_n` de STL.  Pour plus d'informations, consultez [search\_n](../Topic/search_n.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)