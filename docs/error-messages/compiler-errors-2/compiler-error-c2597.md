---
title: Erreur du compilateur C2597 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2597
dev_langs:
- C++
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d110b67adda70ef47cfd9b06addd4370e22c5788
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2597"></a>Erreur du compilateur C2597
référence non conforme à un membre non static 'identificateur'  
  
 Causes possibles :  
  
1.  Un membre non statique est spécifié dans une fonction membre statique. Pour accéder au membre non statique, vous devez transmettre ou créer une instance locale de la classe et utiliser un opérateur d'accès au membre (`.` ou `->`).  
  
2.  L'identificateur spécifié n'est pas un membre d'une classe, d'une structure ni d'une union. Vérifiez l'orthographe de l'identificateur.  
  
3.  Un opérateur d'accès au membre fait référence à une fonction non membre.  
  
4.  L'exemple suivant génère l'erreur C2597 et montre comment la corriger :  
  
```  
// C2597.cpp  
// compile with: /c  
struct s1 {  
   static void func();  
   static void func2(s1&);  
   int i;  
};  
  
void s1::func() {  
   i = 1;    // C2597 - static function can't access non-static data member  
}  
  
// OK - fix by passing an instance of s1  
void s1::func2(s1& a) {  
   a.i = 1;  
}  
```
