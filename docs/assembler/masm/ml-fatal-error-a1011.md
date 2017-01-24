---
title: "ML Fatal Error A1011 | Microsoft Docs"
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
  - "A1011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1011"
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**la directive doit être dans le bloc de contrôle**  
  
 L'assembly a trouvé une directive de premier niveau où il n'est pas prévu.  L'une des directives suivantes a été trouvée :  
  
-   [.ELSE](../../assembler/masm/dot-else.md) sans [.IF](../../assembler/masm/dot-if.md)  
  
-   [.ENDIF](../../assembler/masm/dot-endif.md) sans [.IF](../../assembler/masm/dot-if.md)  
  
-   [.ENDW](../../assembler/masm/dot-endw.md) sans [.WHILE](../../assembler/masm/dot-while.md)  
  
-   [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) sans [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.CONTINUE](../../assembler/masm/dot-continue.md) sans [.WHILE](../../assembler/masm/dot-while.md) ou [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.BREAK](../../assembler/masm/dot-break.md) sans [.WHILE](../../assembler/masm/dot-while.md) ou [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.ELSE](../../assembler/masm/dot-else.md) après `.ELSE`  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)