---
title: "Avertissement du compilateur (niveau 1) C4405 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4405"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4405"
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4405
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : cet identificateur est un mot réservé  
  
 Un mot réservé pour l'assembleur inline est utilisé comme nom de variable.  Ceci peut causer des résultats imprévisibles.  Pour résoudre cet avertissement, évitez de donner aux variables des noms identiques à des mots réservés pour l'assembleur inline.  L'exemple suivant génère l'erreur C4405 :  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```