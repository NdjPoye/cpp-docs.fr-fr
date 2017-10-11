---
title: Erreur du compilateur C2229 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c54e3affb39cb396df1caaafe6450d5c6ac80f6e
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2229"></a>Erreur du compilateur C2229
le type 'identificateur' possède un tableau de taille zéro non conforme  
  
 Un membre d’un champ de structure ou de bits contient un tableau de taille zéro qui n’est pas le dernier membre.  
  
 Étant donné que vous pouvez avoir un tableau de taille zéro comme dernier membre de la structure, vous devez spécifier sa taille lorsque vous allouez la structure.  
  
 Si le tableau de taille zéro n’est pas le dernier membre de la structure, le compilateur ne peut pas calculer le décalage pour les champs restants.  
  
 L’exemple suivant génère l’erreur C2229 :  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```
