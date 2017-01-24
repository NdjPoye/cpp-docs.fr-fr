---
title: "ASSUME | Microsoft Docs"
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
  - "ASSUME"
  - "_assume_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSUME directive"
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ASSUME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active les vérifications des erreurs pour les valeurs de registre.  
  
## Syntaxe  
  
```  
  
      ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## Notes  
 Une fois qu' `ASSUME` mise en œuvre, les surveillée assembleur des modifications apportées aux valeurs des registres donnés.  **ERREUR** génère une erreur si le registre est utilisé.  **RIEN** supprime la vérification des erreurs de registre.  Vous pouvez combiner plusieurs types d'hypothèses dans une instruction.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)