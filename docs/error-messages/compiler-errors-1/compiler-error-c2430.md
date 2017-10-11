---
title: Erreur du compilateur C2430 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2430
dev_langs:
- C++
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f5491d998b9c93fc2041c09c19f8b175d319e4d9
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2430"></a>Erreur du compilateur C2430
plus d’un registre d’index dans 'identificateur'  
  
 Plus d’un Registre est mis à l’échelle. Le compilateur prend en charge l’indexation de mise à l’échelle, mais vous pouvez uniquement mettre à l’échelle un Registre.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2430.  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```
