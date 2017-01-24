---
title: "max_element (STL/CLR) | Microsoft Docs"
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
  - "cliext::max_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_element (fonction) (STL/CLR)"
ms.assetid: c6274bae-1216-4285-b395-254280253dae
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# max_element (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la première occurrence du plus grand élément dans une plage spécifiée où le critère de classement peut être spécifié par un prédicat binaire.  
  
## Syntaxe  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `max_element` de STL.  Pour plus d'informations, consultez [max\_element](../Topic/max_element.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)