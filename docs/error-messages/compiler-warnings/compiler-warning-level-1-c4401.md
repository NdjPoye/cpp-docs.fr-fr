---
title: Compilateur avertissement (niveau 1) C4401 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4401
dev_langs:
- C++
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1042550b4ea176a314e174549ed560cd3ece025
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4401"></a>Avertissement du compilateur (niveau 1) C4401
« champ de bits » : membre est un champ de bits  
  
 Le code assembleur inline tente d’accéder à un membre de champ de bits. Assembleur inline ne peut pas accéder à membres de champ de bits, la dernière limite de compactage avant le membre champ de bits est utilisée.  
  
 Pour éviter cet avertissement, vous devez effectuer un cast en un type approprié, le champ de bits avant de procéder de la référence dans le code assembleur inline. L’exemple suivant génère l’erreur C4401 :  
  
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