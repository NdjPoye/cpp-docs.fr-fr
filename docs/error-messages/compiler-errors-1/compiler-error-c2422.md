---
title: Erreur du compilateur C2422 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65412576c3c1a5e6b8205652d826d0eca6d222e6
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2422"></a>Erreur du compilateur C2422
substitution de segment non conforme dans 'opérande'  
  
 Le code assembleur inline utilise incorrectement un opérateur de substitution de segment (deux-points) sur un opérande.  Plusieurs causes sont possibles :  
  
-   Le Registre précédant l’opérateur n’est pas un Registre de segment.  
  
-   Le Registre précédant l’opérateur n’est pas le seul Registre de segment de l’opérande.  
  
-   L’opérateur de substitution de segment apparaît au sein d’un opérateur d’indirection (crochets).  
  
-   L’expression suivant l’opérateur de substitution de segment n’est pas un opérande immédiat ou un opérande de mémoire.  
  
 L’exemple suivant génère l’erreur C2422 :  
  
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
