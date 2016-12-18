---
title: "remove_copy_if (STL/CLR) | Microsoft Docs"
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
  - "cliext::remove_copy_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_copy_if (fonction) (STL/CLR)"
ms.assetid: 5307f5fe-b6bb-4968-8da1-fea84ab96655
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# remove_copy_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie les éléments d'une plage source à une plage de destination, à l'exception de ceux vérifiant un attribut et qui ne sont pas copiés, sans porter atteinte à l'ordre des éléments restants et retournant la fin d'une nouvelle plage de destination.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction STL `remove_copy_if`.  Pour plus d'informations, consultez [remove\_copy\_if](../Topic/remove_copy_if.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)