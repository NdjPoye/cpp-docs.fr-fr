---
title: Erreur du compilateur C2432 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d89d894738978359fa0cedb9a9da6c4f9781c135
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2432"></a>Erreur du compilateur C2432
référence non conforme à des données 16 bits dans 'identificateur'  
  
 Un registre 16 bits est utilisé comme un index ou un Registre de base. Le compilateur ne prend pas en charge faisant référence à des données 16 bits. les registres 16 bits ne peut pas servir d’index ou la base de registres lors de la compilation de code 32 bits.  
  
 L’exemple suivant génère l’erreur C2432 :  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```
