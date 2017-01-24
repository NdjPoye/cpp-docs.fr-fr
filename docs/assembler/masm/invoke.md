---
title: "INVOKE | Microsoft Docs"
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
  - "Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INVOKE directive"
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# INVOKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle la procédure à l'adresse fournie par *l'expression*, en passant les arguments sur la pile ou dans les registres selon les conventions d'appel standard du type de langage.  
  
## Syntaxe  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## Notes  
 chaque argument passé à la procédure peut être une expression, une paire de registre, ou une expression d'adresse \(une expression précédée par `ADDR`\).  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)