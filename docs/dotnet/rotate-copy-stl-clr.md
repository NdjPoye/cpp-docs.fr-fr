---
title: "rotate_copy (STL/CLR) | Microsoft Docs"
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
  - "cliext::rotate_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rotate_copy (fonction) (STL/CLR)"
ms.assetid: ed697552-130f-474f-9ab6-133332bb2587
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# rotate_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Échange des éléments de plusieurs plages adjacentes dans une plage source et copie les résultats dans une plage de destination.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `rotate_copy` de STL.  Pour plus d'informations, consultez [rotate\_copy](../Topic/rotate_copy.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)