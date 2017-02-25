---
title: "ML Fatal Error A1010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1010"
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**imbrication non couplée de bloc :**  
  
 Un début du bloc n'avait pas de fin correspondante, ou une fin de bloc n'avait pas une début correspondant.  L'une des opérations suivantes peut être impliqué :  
  
-   une directive de premier niveau telle que [.IF](../../assembler/masm/dot-if.md), [.REPEAT](../../assembler/masm/dot-repeat.md), ou [.WHILE](../../assembler/masm/dot-while.md).  
  
-   une directive de conditionnel\-assembly telle que [SI](../../assembler/masm/if-masm.md), [RÉPÉTITION](../../assembler/masm/repeat.md), ou **TANDIS QUE**.  
  
-   Une définition de structure ou d'union.  
  
-   une définition de procédure.  
  
-   une définition de segment.  
  
-   une directive de [POPCONTEXT](../../assembler/masm/popcontext.md) .  
  
-   une directive de conditionnel\-assembly, telle qu' [AUTREMENT](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), ou **ENDIF** sans [SI](../../assembler/masm/if-masm.md)correspondant.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)