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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 852a495406a8baf147fc53262f8fe856fce726b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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