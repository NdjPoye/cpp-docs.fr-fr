---
title: "LOCAL (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOCAL directive"
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LOCAL (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans la première directive, dans une macro, **LOCAL** définit les noms uniques à chaque instance de la macro.  
  
## Syntaxe  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## Notes  
 Dans la deuxième directive, dans une définition de procédure \(**COMMENT**\), **LOCAL** crée des variables pile\-basées qui existent pour la durée de la procédure.  *Le nom* peut être une variable simple ou un tableau contenant les éléments *de nombre* .  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)