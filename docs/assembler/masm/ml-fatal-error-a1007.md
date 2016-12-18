---
title: "ML Fatal Error A1007 | Microsoft Docs"
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
  - "A1007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1007"
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**niveau d'imbrication trop profondément**  
  
 L'assembly a atteint la limite d'imbrication.  La limite est 20 niveaux sauf indication contraire.  
  
 L'une des opérations suivantes a été imbriqués trop profondément :  
  
-   une directive de premier niveau telle que [.IF](../../assembler/masm/dot-if.md), [.REPEAT](../../assembler/masm/dot-repeat.md), ou [.WHILE](../../assembler/masm/dot-while.md).  
  
-   une définition de structure.  
  
-   une directive de conditionnel\-assembly.  
  
-   une définition de procédure.  
  
-   une directive de [PUSHCONTEXT](../../assembler/masm/pushcontext.md) \(la limite est 10\).  
  
-   une définition de segment.  
  
-   un fichier Include.  
  
-   une macro.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)