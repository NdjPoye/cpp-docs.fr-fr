---
title: "for_each (STL/CLR) | Microsoft Docs"
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
  - "cliext::for_each"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for_each (fonction) (STL/CLR)"
ms.assetid: 4c391ecf-cd35-499e-a3f5-35b965e0da9b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for_each (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Applique un objet spécifié de la fonction à chaque élément dans une commande par progression dans une plage et retourne l'objet de la fonction.  
  
## Syntaxe  
  
```  
template<class _InIt, class _Fn1> inline  
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `for_each` de STL.  Pour plus d'informations, consultez [for\_each](../Topic/for_each.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)