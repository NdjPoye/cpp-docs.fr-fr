---
title: Compilateur avertissement (niveau 3) C4334 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4334
dev_langs: C++
helpviewer_keywords: C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7218caa399aec0bd1b9755fb6d0942991732121e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4334"></a>Avertissement du compilateur (niveau 3) C4334
'opérateur' : résultat du décalage 32 bits converti implicitement en 64 bits (était décalage 64 bits destinée ?)  
  
 Le résultat du décalage 32 bits a été implicitement converti en 64 bits et le compilateur soupçonne qu’un décalage 64 bits a été conçu.  Pour résoudre cet avertissement, utilisez le décalage 64 bits, ou explicitement convertir le résultat de la touche MAJ enfoncée en 64 bits.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4334.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```