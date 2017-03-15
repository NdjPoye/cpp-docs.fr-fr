---
title: "search (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::search"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "search (fonction) (STL/CLR)"
ms.assetid: 3317c7f4-9f47-44b8-a7c7-73948a2f83e1
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# search (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la première occurrence d'une séquence dans une fourchette cible dont les éléments sont égaux à ceux dans une séquence d'éléments donnée ou dont les éléments sont équivalents dans une certaine mesure spécifiée par un attribut binaire des éléments de la séquence donnée.  
  
## Syntaxe  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `search` de STL.  Pour plus d'informations, consultez [search](../Topic/search.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)