---
title: "fill (STL/CLR) | Microsoft Docs"
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
  - "cliext::fill"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fill (fonction)"
ms.assetid: eb67241c-9bb3-497e-bec6-639900c60758
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# fill (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Affecte la même nouvelle valeur à chaque élément dans une plage spécifiée.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _Ty> inline  
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `fill` de STL.  Pour plus d'informations, consultez [remplissage](../Topic/fill.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)