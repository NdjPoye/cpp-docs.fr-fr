---
title: "INSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InStr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INSTR directive"
ms.assetid: fc37f6a2-3c95-47b2-b6bb-1066edd25994
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# INSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

recherche la première occurrence de *textitem2* dans *textitem1*.  
  
## Syntaxe  
  
```  
  
name  
 INSTR [[position,]] textitem1, textitem2  
```  
  
## Notes  
 la position de départ est facultative.  Chaque élément de texte peut être une chaîne littéral, une constante précédée par `%`, ou la chaîne retournée par une fonction macro.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)