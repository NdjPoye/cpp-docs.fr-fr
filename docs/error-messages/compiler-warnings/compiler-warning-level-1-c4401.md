---
title: "Avertissement du compilateur (niveau 1) C4401 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4401"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4401"
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4401
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ChampBits' : le membre est un champ de bits  
  
 Du code assembleur inline tente d'accéder à un membre champ de bits.  Le code assembleur inline ne peut pas accéder aux membres champs de bits, donc c'est la dernière limite de compactage avant le membre champ de bits qui est utilisé.  
  
 Pour éviter cet avertissement, effectuez un cast du champ de bits en un type approprié avant d'y faire référence dans du code assembleur inline.  L'exemple suivant génère l'erreur C4401 :  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```