---
title: "ML Fatal Error A1008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1008"
ms.assetid: fe592f9d-c37b-4cd8-a51d-e3c15ddcab83
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**imbrication de macros sans correspondance**  
  
 Une macro n'a pas été terminées avant la fin du fichier ou de l' [ENDM](../../assembler/masm/endm.md) directive se terminant a été trouvée en dehors d'un bloc macro.  
  
 Une cause de cette erreur est l'omission point avant [.REPEAT](../../assembler/masm/dot-repeat.md) ou [.WHILE](../../assembler/masm/dot-while.md).  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)