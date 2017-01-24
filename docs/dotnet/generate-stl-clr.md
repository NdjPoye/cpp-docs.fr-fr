---
title: "generate (STL/CLR) | Microsoft Docs"
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
  - "cliext::generate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generate (fonction) (STL/CLR)"
ms.assetid: 970f209f-31db-47c4-a0bb-4c3e579adb52
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# generate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Affecte les valeurs générées par un objet de la fonction à chaque élément dans une plage.  
  
## Syntaxe  
  
```  
template<class _FwdIt, class _Fn0> inline  
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction `generate` de STL.  Pour plus d'informations, consultez [générer](../Topic/generate.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [algorithm](../dotnet/algorithm-stl-clr.md)