---
title: "STRUCT (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "struct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STRUCT directive"
ms.assetid: 70c3ba6b-00db-461e-8dd9-eafd3ae5b3c8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# STRUCT (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déclare un type de structure avoir *les fielddeclarations*spécifiés.  chaque champ doit être une définition de données valide.  mêmes que [STRUC](../../assembler/masm/struc.md).  
  
## Syntaxe  
  
```  
  
   name STRUCT [[alignment]] [[, NONUNIQUE]]  
fielddeclarations  
name ENDS  
```  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)