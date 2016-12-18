---
title: "upper_bound (STL/CLR) | Microsoft Docs"
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
  - "cliext::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "upper_bound (fonction) (STL/CLR)"
ms.assetid: a377a77b-8005-496e-85ae-b431a9b2f0b9
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la position du premier élément dans une plage ordonnée qui a une valeur supérieure à une valeur spécifiée, où le critère de classement peut être spécifié par un prédicat binaire.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `upper_bound` de STL.  Pour plus d'informations, consultez [upper\_bound](../Topic/upper_bound.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)