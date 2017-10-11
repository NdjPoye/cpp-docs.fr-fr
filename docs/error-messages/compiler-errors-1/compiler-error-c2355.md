---
title: Erreur du compilateur C2355 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2355
dev_langs:
- C++
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 76d274ee94c20502a0ca6f167a9fce1f1dbf9465
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2355"></a>Erreur du compilateur C2355
'this' : ne peut être référencé qu'à l'intérieur de fonctions membres non static ou d'initialiseurs de données membres non static  
  
 Le pointeur `this` est valide uniquement à l'intérieur de fonctions membres non static ou d'initialiseurs de données membres non static. Cette erreur peut intervenir quand la portée de classe d'une définition de fonction membre en dehors de la déclaration de classe n'est pas correctement qualifiée. L'erreur peut également se produire quand le pointeur `this` est utilisé dans une fonction qui n'est pas déclarée dans la classe.  
  
 Pour résoudre ce problème, assurez-vous que la définition de fonction membre correspond à une déclaration de fonction membre dans la classe, et qu'elle n'est pas déclarée static. Pour les initialiseurs de données membres, assurez-vous que les données membres ne sont pas déclarées static.  
  
 L'exemple suivant génère l'erreur C2355 et montre comment la corriger :  
  
```  
// C2355.cpp  
// compile with: /c  
class MyClass {};  
MyClass *p = this;   // C2355  
  
// OK  
class MyClass2 {  
public:  
   void Test() {  
      MyClass2 *p = this;  
   }  
};  
```
