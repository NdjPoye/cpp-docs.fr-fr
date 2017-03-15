---
title: "replace_copy (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::replace_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "replace_copy (fonction) (STL/CLR)"
ms.assetid: b531b49b-b16d-4b04-8f80-74f43dd496a4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# replace_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Examine chaque élément d'une plage source et le remplace s'il correspond à un attribut spécifié lors de la copie du résultat dans une nouvelle plage de destination.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `replace_copy` de STL.  Pour plus d'informations, consultez [replace\_copy](../Topic/replace_copy.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)