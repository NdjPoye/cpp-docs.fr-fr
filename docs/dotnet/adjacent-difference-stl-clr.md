---
title: "adjacent_difference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::adjacent_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adjacent_difference (fonction)"
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# adjacent_difference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine les différences successives entre chaque élément et son prédécesseur dans une plage d'entrée et génère les résultats dans une plage de destination ou calcule le résultat d'une procédure généralisée où l'opération de différence est remplacée par une autre opération binaire, spécifiée.  
  
## Syntaxe  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction numérique STL de `adjacent_difference` Pour plus d'informations, consultez [adjacent\_difference](../Topic/adjacent_difference.md).  
  
## Configuration requise  
 **En\-tête:** \<cliext\/numeric\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [numériques](../dotnet/numeric-stl-clr.md)