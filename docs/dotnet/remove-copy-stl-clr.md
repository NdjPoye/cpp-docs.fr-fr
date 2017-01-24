---
title: "remove_copy (STL/CLR) | Microsoft Docs"
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
  - "cliext::remove_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_copy (fonction) (STL/CLR)"
ms.assetid: 602fd8e3-26f7-491f-bf2c-cddf269f9807
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# remove_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie les éléments d'une plage source à une plage de destination, à l'exception de ceux ayant une valeur spécifiée et qui ne sont pas copiés, sans porter atteinte à l'ordre des éléments restants et retournant la fin d'une nouvelle plage de destination.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `remove_copy` de STL.  Pour plus d'informations, consultez [remove\_copy](../Topic/remove_copy.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)