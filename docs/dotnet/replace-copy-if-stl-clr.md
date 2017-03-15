---
title: "replace_copy_if (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::replace_copy_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "replace_copy_if (fonction) (STL/CLR)"
ms.assetid: 60edf9b8-34e6-4d94-a611-363ef7b7fb80
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# replace_copy_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Examine tous les éléments d'une plage source et les remplace s'ils satisfont un prédicat spécifié lors de la copie du résultat dans une nouvelle plage de destination.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline  
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred, const _Ty% _Val);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `replace_copy_if` de STL.  Pour plus d'informations, consultez [replace\_copy\_if](../Topic/replace_copy_if.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)