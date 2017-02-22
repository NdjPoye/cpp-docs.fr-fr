---
title: "set_symmetric_difference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set_symmetric_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set_symmetric_difference (fonction) (STL/CLR)"
ms.assetid: 4d8997c7-038e-42a8-86d4-81d714ed3775
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# set_symmetric_difference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Associe les éléments appartenant à une seule des deux plages triées sources dans une seule plage triée, où le critère de classement peut être spécifié par un attribut binaire.  
  
## Syntaxe  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `set_symmetric_difference` de STL.  Pour plus d'informations, consultez [set\_symmetric\_difference](../Topic/set_symmetric_difference.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)