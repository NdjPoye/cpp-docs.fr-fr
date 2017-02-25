---
title: "_emit, pseudo-instruction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_emit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_emit (pseudo-instruction)"
  - "définition d'octets (assembleur inline)"
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _emit, pseudo-instruction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 La pseudo\-instruction **\_emit** définit un seul octet à l'emplacement actuel dans le segment de texte actuel.  La pseudo\-instruction **\_emit** ressemble à la directive [DB](../../assembler/masm/db.md) de MASM.  
  
 Le fragment suivant place les octets 0x4A, 0x43 et 0x4B dans le code :  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  Si `_emit` génère des instructions qui modifient les registres et que vous compilez l'application avec les optimisations, le compilateur ne peut pas déterminer quels registres sont affectés.  Par exemple, si `_emit` génère une instruction qui modifie le registre **rax**, le compilateur ne sait pas que **rax** a changé.  Le compilateur peut alors évaluer de façon incorrecte la valeur dans ce registre après l'exécution du code assembleur inline.  Par conséquent, votre application peut présenter un comportement imprévisible lorsqu'elle s'exécute.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)