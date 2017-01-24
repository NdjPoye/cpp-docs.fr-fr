---
title: "nth_element (STL/CLR) | Microsoft Docs"
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
  - "cliext::nth_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nth_element (fonction) (STL/CLR)"
ms.assetid: 19fc1695-62a9-4f85-9920-d153c1c6481f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nth_element (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Partitionne une plage d'éléments, en plaçant correctement le `n`ème élément de la séquence dans la plage de sorte que tous les éléments devant elle lui soient inférieurs ou égaux et tous les éléments qui la suivent dans la séquence lui soient supérieurs ou égaux.  
  
## Syntaxe  
  
```  
template<class _RanIt> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,  
        _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `nth_element` de STL.  Pour plus d'informations, consultez [nth\_element](../Topic/nth_element.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)