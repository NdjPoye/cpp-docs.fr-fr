---
title: "replace_if (STL/CLR) | Microsoft Docs"
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
  - "cliext::replace_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "replace_if (fonction) (STL/CLR)"
ms.assetid: 485ed698-551f-4808-8562-9e32b151786d
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# replace_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Examine chaque élément d'une plage et le remplace s'il satisfait un prédicat spécifié.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _Pr, class _Ty> inline  
    void replace_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred,  
        const _Ty% _Val);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `replace_if` de STL.  Pour plus d'informations, consultez [replace\_if](../Topic/replace_if.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)