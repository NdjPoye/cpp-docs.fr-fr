---
title: "copy (STL/CLR) | Microsoft Docs"
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
  - "cliext::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copy (fonction) (STL/CLR)"
ms.assetid: f6738535-fde6-446e-a797-bf2b457c2bff
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Assigne les valeurs des éléments d'une plage source à une plage de destination, itérant via la séquence source d'éléments et leur assignant de nouvelles positions dans un sens inverse.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `copy` de STL.  Pour plus d'informations, consultez [copy](../Topic/copy.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)