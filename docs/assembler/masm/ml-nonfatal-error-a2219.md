---
title: "ML Nonfatal Error A2219 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2219"
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Incorrect alignement pour l'offset dans le code de déroulement**  
  
 l'opérande pour [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md) et [.SAVEREG](../../assembler/masm/dot-savereg.md) doit être un multiple de 8.  l'opérande pour [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md) et [.SETFRAME](../../assembler/masm/dot-setframe.md) doit être un multiple de 16.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)