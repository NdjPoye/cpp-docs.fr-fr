---
title: "Erreur du compilateur C2422 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2422"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2422"
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2422
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

substitution de segment non conforme dans 'opérande'  
  
 Le code assembleur inline utilise incorrectement un opérateur de substitution de segments \(deux\-points\) sur un opérande.  Plusieurs causes sont possibles :  
  
-   Le registre précédant l'opérateur n'est pas un registre de segment.  
  
-   Le registre précédant l'opérateur n'est pas le seul registre de segment de l'opérande.  
  
-   L'opérateur de substitution de segments apparaît dans un opérateur d'indirection \(crochets\).  
  
-   L'expression suivant l'opérateur de substitution de segments n'est pas un opérande immédiat ou un opérande de mémoire.  
  
 L'exemple suivant génère l'erreur C2422 :  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```