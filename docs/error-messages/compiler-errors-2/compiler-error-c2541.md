---
title: Erreur du compilateur C2541 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2541
dev_langs:
- C++
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 24bb63554f67d5496e46fb1ab8fa7133fadc38c5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2541"></a>Erreur du compilateur C2541
'delete' : delete : Impossible de supprimer les objets qui ne sont pas des pointeurs  
  
 Le [supprimer](../../cpp/delete-operator-cpp.md) opérateur a été utilisé sur un objet qui n’est pas un pointeur.  
  
 L’exemple suivant génère l’erreur C2541 :  
  
```  
// C2541.cpp  
int main() {  
   int i;  
   delete i;   // C2541 i not a pointer  
  
   // OK  
   int *ip = new int;  
   delete ip;  
}  
```
