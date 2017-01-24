---
title: "Directives Reference | Microsoft Docs"
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
  - "Directives Reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), directives reference"
ms.assetid: da6efcd1-18f7-41de-81cd-a002a02f9a22
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**x64**  
  
||||  
|-|-|-|  
|[.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)|[.ENDPROLOG](../../assembler/masm/dot-endprolog.md)|[COMMENT](../../assembler/masm/proc.md)|  
|[.PUSHFRAME](../../assembler/masm/dot-pushframe.md)|[.PUSHREG](../../assembler/masm/dot-pushreg.md)|[.SAVEREG](../../assembler/masm/dot-savereg.md)|  
|[.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)|[.SETFRAME](../../assembler/masm/dot-setframe.md)||  
  
### noms de code  
  
|||  
|-|-|  
|[ALIGNEZ](../../assembler/masm/align-masm.md)|[MÊME](../../assembler/masm/even.md)|  
|[NOM](../../assembler/masm/label-masm.md)|[ORG](../../assembler/masm/org.md)|  
  
### Assembly conditionnelle  
  
||||  
|-|-|-|  
|[AUTREMENT](../../assembler/masm/else-masm.md)|[ELSEIF](../../assembler/masm/elseif-masm.md)|[ELSEIF2](../../assembler/masm/elseif2.md)|  
|[SI](../../assembler/masm/if-masm.md)|[IF2](../../assembler/masm/if2.md)|[IFB](../../assembler/masm/ifb.md)\/[IFNB](../../assembler/masm/ifnb.md)|  
|[IFDEF](../../assembler/masm/ifdef.md)\/[IFNDEF](../../assembler/masm/ifndef.md)|[IFDIF](../../assembler/masm/ifdif.md)\/[IFDIF &#91;&#93; &#91;&#93; I](../../assembler/masm/ifdif.md)|[IFE](../../assembler/masm/ife.md)|  
|[IFIDN](../../assembler/masm/ifidn.md)\/[IFIDN &#91;&#93; &#91;&#93; I](../../assembler/masm/ifidn.md)|||  
  
### flux de contrôle conditionnel  
  
||||  
|-|-|-|  
|[.BREAK](../../assembler/masm/dot-break.md)|[.CONTINUE](../../assembler/masm/dot-continue.md)|[.ELSE](../../assembler/masm/dot-else.md)|  
|[.ELSEIF](../../assembler/masm/dot-if.md)|[.ENDIF](../../assembler/masm/dot-endif.md)|[.ENDW](../../assembler/masm/dot-endw.md)|  
|[.IF](../../assembler/masm/dot-if.md)|[.REPEAT](../../assembler/masm/dot-repeat.md)|[.UNTIL](../../assembler/masm/dot-until.md)|  
|[.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)|[.WHILE](../../assembler/masm/dot-while.md)||  
  
### erreur conditionnelle  
  
||||  
|-|-|-|  
|[.ERR](../../assembler/masm/dot-err.md)|[.ERR2](../../assembler/masm/dot-err2.md)|[.ERRB](../../assembler/masm/dot-errb.md)|  
|[.ERRDEF](../../assembler/masm/dot-errdef.md)|[.ERRDIF](../../assembler/masm/dot-errdif.md)\/[.ERRDIF &#91;I&#93; &#91;&#93;&#93;](../../assembler/masm/dot-errdif.md)|[.ERRE](../../assembler/masm/dot-erre.md)|  
|[.ERRIDN](../../assembler/masm/dot-erridn.md)\/[.ERRIDN &#91;&#93; &#91;&#93; I](../../assembler/masm/dot-erridn.md)|[.ERRNB](../../assembler/masm/dot-errnb.md)|[.ERRNDEF](../../assembler/masm/dot-errndef.md)|  
|[.ERRNZ](../../assembler/masm/dot-errnz.md)|||  
  
### allocation de données  
  
||||  
|-|-|-|  
|[ALIGNEZ](../../assembler/masm/align-masm.md)|[OCTET](../../assembler/masm/byte-masm.md)\/[SBYTE](../../assembler/masm/sbyte-masm.md)|[valeur DWORD](../../assembler/masm/dword.md)\/[SDWORD](../../assembler/masm/sdword.md)|  
|[MÊME](../../assembler/masm/even.md)|[FWORD](../../assembler/masm/fword.md)|[NOM](../../assembler/masm/label-masm.md)|  
|[ORG](../../assembler/masm/org.md)|[QWORD](../../assembler/masm/qword.md)|[REAL4](../../assembler/masm/real4.md)|  
|[REAL8](../../assembler/masm/real8.md)|[REAL10](../../assembler/masm/real10.md)|[TBYTE](../../assembler/masm/tbyte.md)|  
|[WORD](../../assembler/masm/word.md)\/[ÉPÉE](../../assembler/masm/sword.md)|||  
  
### Équivaut  
  
||  
|-|  
|[\=](../../assembler/masm/equal.md)|  
|[EQU](../../assembler/masm/equ.md)|  
|[TEXTEQU](../../assembler/masm/textequ.md)|  
  
### répertorier le contrôle  
  
||||  
|-|-|-|  
|[.CREF](../../assembler/masm/dot-cref.md)|[.LIST](../../assembler/masm/dot-list.md)|[.LISTALL](../../assembler/masm/dot-listall.md)|  
|[.LISTIF](../../assembler/masm/dot-listif.md)|[.LISTMACRO](../../assembler/masm/dot-listmacro.md)|[.LISTMACROALL](../../assembler/masm/dot-listmacroall.md)|  
|[.NOCREF](../../assembler/masm/dot-nocref.md)|[.NOLIST](../../assembler/masm/dot-nolist.md)|[.NOLISTIF](../../assembler/masm/dot-nolistif.md)|  
|[.NOLISTMACRO](../../assembler/masm/dot-nolistmacro.md)|[PG](../../assembler/masm/page.md)|[SOUS\-TITRE](../../assembler/masm/subtitle.md)|  
|[.TFCOND](../../assembler/masm/dot-tfcond.md)|[TITRE](../../assembler/masm/title.md)||  
  
### Macros  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[EXITM](../../assembler/masm/exitm.md)|[Goto](../../assembler/masm/goto-masm.md)|  
|[GENS DU PAYS](../../assembler/masm/local-masm.md)|[MACRO](../../assembler/masm/macro.md)|[PURGE](../../assembler/masm/purge.md)|  
  
### Divers  
  
||||  
|-|-|-|  
|[ALIAS](../../assembler/masm/alias-masm.md)|[SUPPOSEZ](../../assembler/masm/assume.md)|[COMMENTAIRE](../../assembler/masm/comment-masm.md)|  
|[ÉCHO](../../assembler/masm/echo.md)|[FIN](../../assembler/masm/end-masm.md)|[.FPO](../../assembler/masm/dot-fpo.md)|  
|[COMPRENEZ](../../assembler/masm/include-masm.md)|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[MMWORD](../../assembler/masm/mmword.md)|  
|[OPTION](../../assembler/masm/option-masm.md)|[POPCONTEXT](../../assembler/masm/popcontext.md)|[PUSHCONTEXT](../../assembler/masm/pushcontext.md)|  
|[.RADIX](../../assembler/masm/dot-radix.md)|[.SAFESEH](../../assembler/masm/dot-safeseh.md)|[XMMWORD](../../assembler/masm/xmmword.md)|  
|[YMMWORD](../../assembler/masm/ymmword.md)|||  
  
### Procédures  
  
||||  
|-|-|-|  
|[ENDP](../../assembler/masm/endp.md)|[APPELEZ](../../assembler/masm/invoke.md)|[COMMENT](../../assembler/masm/proc.md)|  
|[PROTO](../../assembler/masm/proto.md)|||  
  
### Processeur  
  
||||  
|-|-|-|  
|[.386](../../assembler/masm/dot-386.md)|[.386P](../../assembler/masm/dot-386p.md)|[.387](../../assembler/masm/dot-387.md)|  
|[.486](../../assembler/masm/dot-486.md)|[.486P](../../assembler/masm/dot-486p.md)|[.586](../../assembler/masm/dot-586.md)|  
|[.586P](../../assembler/masm/dot-586p.md)|[.686](../../assembler/masm/dot-686.md)|[.686P](../../assembler/masm/dot-686p.md)|  
|[. K3D](../../assembler/masm/dot-k3d.md)|[.MMX](../../assembler/masm/dot-mmx.md)|[.XMM](../../assembler/masm/dot-xmm.md)|  
  
### blocs de répétition  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[FOR](../../assembler/masm/for-masm.md)|[FORC](../../assembler/masm/forc.md)|  
|[Goto](../../assembler/masm/goto-masm.md)|[RÉPÉTITION](../../assembler/masm/repeat.md)|[TANDIS QUE](../../assembler/masm/while-masm.md)|  
  
### Portée  
  
||||  
|-|-|-|  
|[COMM.](../../assembler/masm/comm.md)|[EXTERN](../../assembler/masm/extern-masm.md)|[EXTERNDEF](../../assembler/masm/externdef.md)|  
|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[PUBLIC](../../assembler/masm/public-masm.md)||  
  
### segment  
  
||||  
|-|-|-|  
|[.ALPHA](../../assembler/masm/dot-alpha.md)|[SUPPOSEZ](../../assembler/masm/assume.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|  
|[FIN](../../assembler/masm/end-masm.md)|[SE TERMINE](../../assembler/masm/ends-masm.md)|[GROUP](../../assembler/masm/group.md)|  
|[SEGMENT](../../assembler/masm/segment.md)|[.SEQ](../../assembler/masm/dot-seq.md)||  
  
### segment simplifié  
  
||||  
|-|-|-|  
|[.CODE](../../assembler/masm/dot-code.md)|[.CONST](../../assembler/masm/dot-const.md)|[.DATA](../../assembler/masm/dot-data.md)|  
|[.DATA ?](../../assembler/masm/dot-data-q.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|[.EXIT](../../assembler/masm/dot-exit.md)|  
|[.FARDATA](../../assembler/masm/dot-fardata.md)|[.FARDATA ?](../../assembler/masm/dot-fardata-q.md)|[.MODEL](../../assembler/masm/dot-model.md)|  
|[.STACK](../../assembler/masm/dot-stack.md)|[.STARTUP](../../assembler/masm/dot-startup.md)||  
  
### Chaîne  
  
|||  
|-|-|  
|[CATSTR](../../assembler/masm/catstr.md)|[INSTR](../../assembler/masm/instr.md)|  
|[SIZESTR](../../assembler/masm/sizestr.md)|[SUBSTR](../../assembler/masm/substr.md)|  
  
### structure et enregistrement  
  
||||  
|-|-|-|  
|[SE TERMINE](../../assembler/masm/ends-masm.md)|[ENREGISTREMENT](../../assembler/masm/record-masm.md)|[STRUCT](../../assembler/masm/struct-masm.md)|  
|[TYPEDEF](../../assembler/masm/typedef-masm.md)|[UNION](../../assembler/masm/union.md)||  
  
## Voir aussi  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)