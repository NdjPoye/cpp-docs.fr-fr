---
title: Erreur du compilateur C2046 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2046
dev_langs:
- C++
helpviewer_keywords:
- C2046
ms.assetid: f0c8f9dd-dbd7-4c4a-8838-fde54208ec71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20b41b2317d98364122118f3d6c6e66a0a0d73b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2046"></a>Erreur du compilateur C2046
instruction case non conforme  
  
 Le mot clé `case` ne peut être spécifié que dans une instruction `switch` .  
  
 L’exemple suivant génère l’erreur C2046 :  
  
```  
// C2046.cpp  
int main() {  
   case 0:   // C2046  
}  
```  
  
 Solution possible :  
  
```  
// C2046b.cpp  
int main() {  
   int i = 0;  
  
   switch(i) {  
      case 0:  
      break;  
  
      default:  
      break;  
   }  
}  
```