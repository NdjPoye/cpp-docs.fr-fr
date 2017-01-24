---
title: "generate_n (STL/CLR) | Microsoft Docs"
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
  - "cliext::generate_n"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generate_n (fonction) (STL/CLR)"
ms.assetid: 2f56e649-7a6f-4861-ae49-d0b25f5cd50c
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# generate_n (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Affecte les valeurs générées par une fonction d'objet à un nombre spécifié d'éléments est une plage et renvoie à la position correspondant à celle après la dernière valeur affectée.  
  
## Syntaxe  
  
```  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `generate_n` de STL.  Pour plus d'informations, consultez [generate\_n](../Topic/generate_n.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)