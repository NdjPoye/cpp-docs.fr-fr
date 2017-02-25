---
title: "Directives de macro MASM dans l&#39;assembly inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "directives, macros"
  - "assembleur inline, directives de macro"
  - "macros, directives"
  - "MASM (Microsoft Macro Assembler), directives de macro de l'assembleur inline"
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Directives de macro MASM dans l&#39;assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 L'assembleur inline n'est pas un macro\-assembleur.  Vous ne pouvez pas utiliser de directives relatives aux macros MASM \(**MACRO**, `REPT`, **IRC**, `IRP`, et `ENDM`\) ou d'opérateurs macro \(**\<\>\!**, **&**, `%` et `.TYPE`\).  Un bloc `__asm` peut cependant utiliser des directives de préprocesseur C.  Pour plus d'informations, consultez [Utilisation de C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)