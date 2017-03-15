---
title: "min_element (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::min_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "min_element (fonction) (STL/CLR)"
ms.assetid: 2a9c6828-9722-454f-9c10-d4a184d4d21b
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# min_element (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la première occurrence du plus petit élément dans une plage spécifiée où le critère de classement peut être spécifié par un prédicat binaire.  
  
## Syntaxe  
  
```  
template<class _FwdIt> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `min_element` de STL.  Pour plus d'informations, consultez [min\_element](../Topic/min_element.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)