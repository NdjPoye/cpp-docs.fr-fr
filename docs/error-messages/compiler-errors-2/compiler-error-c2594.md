---
title: Erreur du compilateur C2594 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6a73e5202b90a0bc436d93be142162531c6d204
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2594"></a>Erreur du compilateur C2594
'opérateur' : conversions ambiguës de 'type1' en 'type2'  
  
 Aucune conversion de *type1* à *type2* a été plus directe qu’une autre. Nous vous suggérons deux solutions possibles à la conversion de *type1* à *type2*. La première option consiste à définir une conversion directe de *type1* à *type2*, et la deuxième option consiste à spécifier une séquence de conversions de *type1* à  *type2*.  
  
 L’exemple suivant génère l’erreur C2594. La résolution suggérée pour l’erreur est une séquence de conversions :  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```
