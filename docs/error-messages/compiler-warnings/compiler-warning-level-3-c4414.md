---
title: Compilateur avertissement (niveau 3) C4414 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4414
dev_langs:
- C++
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76745a1cf505a685bcb9a6d2e74faf98bad77556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4414"></a>Avertissement du compilateur (niveau 3) C4414
'fonction' : saut de type short vers la fonction converti en near  
  
 Sauts courts génèrent une instruction compacte qui effectue un branchement vers une adresse dans une plage limitée à partir de l’instruction. L’instruction inclut un court offset qui représente la distance entre le saut et l’adresse cible, la définition de fonction. Lors de la liaison, une fonction peut être déplacées ou soumises à optimisations au moment de la liaison qui amène la fonction à être déplacé hors de la plage est accessible à partir d’un offset court. Le compilateur doit générer un enregistrement spécial pour le saut, qui requiert une instruction jump NEAR ou bien. Le compilateur a effectué la conversion.  
  
 Par exemple, le code suivant génère l’erreur C4414 :  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```