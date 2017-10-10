---
title: Erreur du compilateur C2663 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a9efe20b4a80b9ff6f337d32acd35320125008dc
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2663"></a>Erreur du compilateur C2663
'fonction' : nombre surcharges n’ont pas de conversion autorisée pour le pointeur 'this'  
  
 Le compilateur n’a pas pu convertir `this` à une des versions surchargées de la fonction membre.  
  
 Cette erreur peut être provoquée en appelant un non -`const` fonction membre sur une `const` objet.  Solutions possibles :  
  
1.  Supprimer le `const` à partir de la déclaration d’objet.  
  
2.  Ajouter `const` à une des surcharges de fonction membre.  
  
 L’exemple suivant génère l’erreur C2663 :  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```
