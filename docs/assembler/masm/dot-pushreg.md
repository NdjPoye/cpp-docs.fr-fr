---
title: ".PUSHREG | Microsoft Docs"
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
  - ".PUSHREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHREG directive"
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère une entrée de code de déroulement d' `UWOP_PUSH_NONVOL` pour le nombre spécifié de registre à l'aide de l'offset actif en prologue.  
  
## Syntaxe  
  
```  
.PUSHREG register  
```  
  
## Notes  
 .PUSHREG Permet aux utilisateurs de ml64.exe pour spécifier comment une fonction de frame se déroule, et uniquement autorisé dans le prologue, qui s'étend de la déclaration de FRAME de [PROC](../../assembler/masm/proc.md) à la directive de [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) .  Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`.  .PUSHREG Doit être précédé de l'instruction qui implémentent réellement les actions devant être déroulé.  Il est conseillé d'encapsuler les directives de déroulement et le code qu'ils sont censées les dérouler dans une macro pour garantir le contrat.  
  
 Pour plus d'informations, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Exemples  
  
### Description  
 L'exemple suivant montre comment effectuer des tegisters non volatiles.  
  
### Code  
  
```  
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
Example1 PROC FRAME  
   push r10  
.pushreg r10  
   push r15  
.pushreg r15  
   push rbx  
.pushreg rbx  
   push rsi  
.pushreg rsi  
.endprolog  
   ; rest of function ...  
   ret  
Example1 ENDP  
_text ENDS  
END  
```  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)