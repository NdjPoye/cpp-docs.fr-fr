---
title: "includes (STL/CLR) | Microsoft Docs"
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
  - "cliext::includes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includes (fonction) (STL/CLR)"
ms.assetid: 566307f4-92e0-4acc-ba49-caa48f3ec744
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# includes (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si une plage ordonnée contient tous les éléments contenus dans une plage triée ensuite, dans laquelle le classement ou le critère d'équivalence entre les éléments peuvent être spécifiés par un attribut binaire.  
  
## Syntaxe  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `includes` de STL.  Pour plus d'informations, consultez [includes](../Topic/includes.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)