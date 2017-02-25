---
title: "Macros MASM | Microsoft Docs"
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
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Macros MASM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour simplifier l'utilisation des [Pseudo\-opérations brutes](../build/raw-pseudo-operations.md), vous disposez d'un jeu de macros, défini dans ksamd64.inc, qui peut être utilisé pour créer des prologues et des épilogues de procédures standard.  
  
## Notes  
  
|Macro|Description|  
|-----------|-----------------|  
|alloc\_stack\(n\)|Alloue un frame de pile de n octets \(à l'aide de sub rsp, n\) et émet les informations de déroulement appropriées \(.allocstack n\)|  
|save\_reg reg, loc|Enregistre un fichier .reg de registre non volatil sur la pile au niveau de l'emplacement de l'offset du RSP et informations de déroulement appropriées  \(.savereg reg, loc\).|  
|push\_reg reg|Exécute un push d'un fichier .reg de registre non volatil sur la pile et émet les informations de déroulement appropriées  \(.pushreg reg\).|  
|rex\_push\_reg reg|Enregistrez un registre non\-volatile sur la pile à l'aide d'une transmission de type push de 2 octets, et émet des informations pertinentes de déroulement \(repérage de .pushreg\) cela doivent être utilisées si la transmission de type push est la première instruction dans la fonction pour garantir que la fonction est chaude \- patchable.|  
|save\_xmm128 reg, loc|Enregistre un fichier .reg de registre XMM non volatil sur la pile au niveau de l'emplacement de l'offset du RSP compensez loc et émet les informations de déroulement appropriées \(.savexmm128 reg, loc\)|  
|set\_frame reg, offset|Définit le fichier .reg du registre du frame comme le RSP \+ l'offset \(à l'aide de mov ou de lea\) et émet les informations de déroulement appropriées \(.set\_frame reg, offset\)|  
|push\_eflags|Exécute un push sur les eflags avec une instruction pushfq et émet les informations de déroulement appropriées \(.alloc\_stack 8\)|  
  
 Voici un exemple de prologue de fonction avec une utilisation correcte des macros :  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
SavedRdi dq ?; saved register RDI   
SavedRsi dq ?; saved register RSI   
SkFrame ends  
  
sampleFrame struct  
Filldq?; fill to 8 mod 16  
SavedRdidq?; Saved Register RDI   
SavedRsi  dq?; Saved Register RSI  
sampleFrame ends  
  
sample2 PROC FRAME  
alloc_stack(sizeof sampleFrame)  
save_reg rdi, sampleFrame.SavedRdi  
save_reg rsi, sampleFrame.SavedRsi  
.end_prolog  
  
; function body  
  
mov rsi, sampleFrame.SavedRsi[rsp]  
mov rdi, sampleFrame.SavedRdi[rsp]  
  
; Here’s the official epilog  
  
add rsp, (sizeof sampleFrame)  
ret  
sample2 ENDP  
```  
  
## Voir aussi  
 [Déroulement de l'assistance pour MASM](../build/unwind-helpers-for-masm.md)