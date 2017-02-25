---
title: "Vue d&#39;ensemble de l&#39;assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), appeler l'assembleur inline"
  - "assembleur inline"
  - "assembleur inline, assembleur inline"
  - "appeler l'assembleur inline"
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Vue d&#39;ensemble de l&#39;assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 L'assembleur inline vous permet d'incorporer des instructions en langage assembleur dans vos programmes source C et C\+\+ sans étapes ensemble et des liens supplémentaires.  L'assembleur inline est intégrée dans le compilateur, vous n'avez pas besoin d'un assembleur distinct tels que Microsoft Macro Assembler \(MASM\).  
  
 Comme assembly distinct et les opérations de liaison ne nécessite pas l'assembleur inline, il est plus pratique que d'un assembleur distinct.  Le code assembleur inline peut utiliser n'importe quel nom de variable ou une fonction C ou C\+\+ qui est dans la portée, il est donc facile à les intégrer dans le code C et C\+\+ de votre programme.  Et étant donné que le code de l'assembly peut être mélangé avec des instructions de C et C\+\+, il peut effectuer des tâches difficile ou impossible en C ou C\+\+ uniquement.  
  
 Le  [\_\_asm](../../assembler/inline/asm.md) mot\-clé appelle l'assembleur inline et peuvent apparaître partout où une instruction C ou C\+\+ est légale.  Il ne peut pas apparaître seul.  Il doit être suivi par une instruction, un groupe d'instructions entouré accolades ou, tout au moins, une paire d'accolades vide.  Le terme « `__asm` bloc » ici fait référence à toute instruction ou un groupe d'instructions, ou non dans les accolades.  
  
 Le code suivant est une simple  `__asm`bloc entouré accolades.  \(Le code est une séquence de prologue de fonction personnalisée.\)  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 Vous pouvez également mettre  `__asm`devant chaque instruction assembly :  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 Étant donné que la  `__asm`le mot clé est un séparateur d'instruction, vous pouvez également placer des instructions d'assemblage sur la même ligne :  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)