---
title: "equal_range (STL/CLR) | Microsoft Docs"
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
  - "cliext::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_range (fonction) (STL/CLR)"
ms.assetid: 1b2e76c3-6b52-486d-9785-2639b54277fd
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche une paire de position dans une plage triée, la première inférieure ou équivalente à la position d'un élément spécifié et le deuxième supérieur à la position de l'élément, où le sens de l'équivalence ou du tri utilisé pour générer les positions dans la séquence peut être spécifié par un attribut binaire.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `equal_range` de STL.  Pour plus d'informations, consultez [equal\_range](../Topic/equal_range.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)