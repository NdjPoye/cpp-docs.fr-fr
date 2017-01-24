---
title: "inplace_merge (STL/CLR) | Microsoft Docs"
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
  - "cliext::inplace_merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inplace_merge (fonction) (STL/CLR)"
ms.assetid: e6948c03-8c5b-4a7c-915c-0a531946a321
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# inplace_merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Associe les éléments de deux plages triées consécutives dans une seule plage triée, où le respect du classement peut être spécifié par un attribut binaire.  
  
## Syntaxe  
  
```  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte de la même manière que la fonction `inplace_merge` de STL pour plus d'informations, consultez [inplace\_merge](../Topic/inplace_merge.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)