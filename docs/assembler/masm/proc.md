---
title: "PROC | Microsoft Docs"
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
  - "PROC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROC directive"
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PROC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le début et de fin d'un bloc PROCEDURE appelé *nom*.  Les instructions du bloc peuvent être appelées avec l'instruction d' **APPEL** la directive ou d' [APPELEZ](../../assembler/masm/invoke.md) .  
  
## Syntaxe  
  
```  
  
   label PROC [[distance]] [[langtype]] [[visibility]] [[<prologuearg>]]   
[[USES reglist]] [[, parameter [[:tag]]]]...  
[FRAME [:ehandler-address] ]  
statements  
label ENDP  
```  
  
## Notes  
 \[FRAME \[:*l'ehandler\-adresse*\]\] est uniquement valide avec ml64.exe, et fait pour générer une entrée de table de fonction dans .pdata et déroule MASM les informations dans .xdata pour le comportement de déroulement de la gestion structurée des exceptions d'une fonction.  
  
 Lorsque l'attribut de **FRAME** est utilisé, il doit être suivi par une directive de [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) .  
  
 Consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md) pour plus d'informations sur l'utilisation ml64.exe.  
  
## Exemple  
  
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
  
 Le code ci\-dessus émet le tableau de fonction suivant et déroulera des informations :  
  
```  
FileHeader->Machine 34404  
Dumping Unwind Information for file ex2.exe  
  
.pdata entry 1 0x00001000 0x00001023  
  
  Unwind data: 0x00002000  
  
    Unwind version: 1  
    Unwind Flags: None  
    Size of prologue: 0x08  
    Count of codes: 3  
    Frame register: rbp  
    Frame offset: 0x0  
    Unwind codes:  
  
      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00  
      Code offset: 0x05, ALLOC_SMALL, size=0x10  
      Code offset: 0x01, PUSH_NONVOL, register=rbp  
```  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)