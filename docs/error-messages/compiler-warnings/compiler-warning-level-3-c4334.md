---
title: "Avertissement du compilateur (niveau 3) C4334 | Microsoft Docs"
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
  - "C4334"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4334"
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4334
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : résultat du décalage 32 bits converti implicitement en 64 bits \(le décalage 64 bits est\-il intentionnel ?\)  
  
 Le résultat du décalage 32 bits a été converti implicitement en 64 bits, et le compilateur soupçonne qu'un décalage 64 bits était intentionnel.  Pour résoudre cet avertissement, utilisez le décalage 64 bits ou effectuez un cast explicite du résultat du décalage en 64 bits.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4334 :  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```