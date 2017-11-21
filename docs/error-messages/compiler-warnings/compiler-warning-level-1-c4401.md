---
title: Compilateur avertissement (niveau 1) C4401 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4401
dev_langs: C++
helpviewer_keywords: C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cabb50ca025390cd00f4c9db68f3aa97d606fa57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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