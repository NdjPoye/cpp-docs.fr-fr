---
title: "Pseudo-op&#233;rations brutes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pseudo-op&#233;rations brutes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les pseudo\-opérations.  
  
## Notes  
  
|Pseudo\-opération|Description|  
|-----------------------|-----------------|  
|PROC FRAME \[:ehandler\]|Demande à MASM de générer une table de fonctions d'entrée dans .pdata et de débobiner des informations dans .xdata pour le comportement de déroulement de la gestion structurée des exceptions d'une fonction.  Si ehandler est présent, cette procédure est insérée dans le fichier .xdata en tant que gestionnaire spécifique au langage.<br /><br /> Lorsque l'attribut FRAME est utilisé, il doit être suivi d'une directive .ENDPROLOG.  Si la fonction est une fonction feuille \(comme défini dans [Types de fonctions](../build/function-types.md)\), l'attribut FRAME est inutile, tout comme le reste de ces pseudo\-opérations.|  
|.PUSHREG reg|Génère une entrée de code de déroulement UWOP\_PUSH\_NONVOL pour le numéro de registre spécifié à l'aide de l'offset actuel dans le prologue.<br /><br /> Cette opération ne doit être utilisée qu'avec les registres d'entiers non volatils.  Pour les push de registres volatils, utilisez plutôt .ALLOCSTACK 8|  
|.SETFRAME reg, offset|Remplit le champ du registre du frame et l'offset dans les informations de déroulement à l'aide du registre et de l'offset spécifiés.  L'offset doit être un multiple de 16 et inférieur ou égal à 240.  Cette directive génère également une entrée de code de déroulement UWOP\_SET\_FPREG pour le registre spécifié à l'aide de l'offset de prologue actuel.|  
|.ALLOCSTACK size|Génère UWOP\_ALLOC\_SMALL ou UWOP\_ALLOC\_LARGE avec la taille spécifiée pour l'offset actuel dans le prologue.<br /><br /> L'opérande de taille doit être un multiple de 8.|  
|.SAVEREG reg, offset|Génère une entrée de code de déroulement UWOP\_SAVE\_NONVOL ou UWOP\_SAVE\_NONVOL\_FAR pour le registre et l'offset spécifiés à l'aide de l'offset de prologue actuel.  MASM choisira l'encodage le plus efficace.<br /><br /> L'offset doit être positif et un multiple de 8.  L'offset est relatif à la base de la frame de la procédure qui est en général dans RSP ou, si vous utilisez un pointeur de frame, le pointeur de frame non cadré.|  
|.SAVEXMM128 reg, offset|Génère une entrée de code de déroulement UWOP\_SAVE\_XMM128 ou UWOP\_SAVE\_XMM128\_FAR pour le registre XMM et l'offset spécifiés à l'aide de l'offset de prologue actuel.  MASM choisira l'encodage le plus efficace.<br /><br /> L'offset doit être positif et un multiple de 16.  L'offset est relatif à la base de la frame de la procédure qui est en général dans RSP ou, si vous utilisez un pointeur de frame, le pointeur de frame non cadré.|  
|.PUSHFRAME \[code\]|Génère une entrée de code de déroulement UWOP\_PUSH\_MACHFRAME.  Si le code facultatif est spécifié, l'entrée de code de déroulement reçoit un modificateur de 1.  Sinon, le modificateur est 0.|  
|.ENDPROLOG|Signale la fin des déclarations de prologue.  Doit se produire dans les 255 premiers octets de la fonction.|  
  
 Voici un exemple de prologue de fonction avec une utilisation correcte de la plupart des codes d'opération :  
  
```  
sample PROC FRAME     
   db      048h; emit a REX prefix, to enable hot-patching  
push rbp  
.pushreg rbp  
sub rsp, 040h  
.allocstack 040h     
lea rbp, [rsp+020h]  
.setframe rbp, 020h  
movdqa [rbp], xmm7  
.savexmm128 xmm7, 020h;the offset is from the base of the frame  
;not the scaled offset of the frame  
mov [rbp+018h], rsi  
.savereg rsi, 038h  
mov [rsp+010h], rdi  
.savereg rdi, 010h; you can still use RSP as the base of the frame  
; or any other register you choose  
.endprolog  
  
; you can modify the stack pointer outside of the prologue (similar to alloca)  
; because we have a frame pointer.  
; if we didn’t have a frame pointer, this would be illegal  
; if we didn’t make this modification,  
; there would be no need for a frame pointer  
  
sub rsp, 060h  
  
; we can unwind from the following AV because of the frame pointer  
  
mov rax, 0  
mov rax, [rax] ; AV!  
  
; restore the registers that weren’t saved with a push  
; this isn’t part of the official epilog, as described in section 2.5  
  
movdqa xmm7, [rbp]  
mov rsi, [rbp+018h]  
mov rdi, [rbp-010h]  
  
; Here’s the official epilog  
  
lea rsp, [rbp-020h]  
pop rbp  
ret  
sample ENDP  
```  
  
## Voir aussi  
 [Déroulement de l'assistance pour MASM](../build/unwind-helpers-for-masm.md)