---
title: "iter_swap (STL/CLR) | Microsoft Docs"
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
  - "cliext::iter_swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iter_swap (fonction) (STL/CLR)"
ms.assetid: 9809c9f5-2ca6-4e9e-97c1-d7973d3134f8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# iter_swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Echange deux valeurs référencés par une paire d'itérateurs spécifiés.  
  
## Syntaxe  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    void iter_swap(_FwdIt1 _Left, _FwdIt2 _Right);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `iter_swap` de STL.  Pour plus d'informations, consultez [iter\_swap](../Topic/iter_swap.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)