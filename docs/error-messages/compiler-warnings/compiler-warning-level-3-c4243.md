---
title: Compilateur avertissement (niveau 3) C4243 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4243
dev_langs: C++
helpviewer_keywords: C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 527dbbc55fca3f8c602704472ba17a31d54b4b3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4243"></a>Avertissement du compilateur (niveau 3) C4243
' type de conversion' existe à partir de 'type1' en 'type2', mais n’est pas accessible  
  
 Un pointeur vers une classe dérivée est converti en un pointeur vers une classe de base, mais la classe dérivée hérite de la classe de base avec un accès privé ou protégé.  
  
 L’exemple suivant génère l’erreur C4243 :  
  
```  
// C4243.cpp  
// compile with: /W3  
// C4243 expected  
struct B {  
   int f() {  
      return 0;  
   };  
};  
  
struct D : private B {};  
struct E : public B {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   int (D::* d)() = (int(D::*)()) &B::f;   
   d;  
  
   int (E::* e)() = (int(E::*)()) &B::f; // OK  
   e;  
}  
```