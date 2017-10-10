---
title: Erreur du compilateur C2027 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2a2fec9194858127ca08ecc0a891a81a91de48fa
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2027"></a>Erreur du compilateur C2027
utilisation d’un type non défini 'type'  
  
 Un type ne peut pas être utilisé tant qu’elle est définie. Pour résoudre cette erreur, assurez-vous que le type est entièrement défini avant de le référencer.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2027.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## <a name="example"></a>Exemple  
 Il est possible de déclarer un pointeur vers un type déclaré mais pas défini.  Mais Visual C++ n’autorise pas une référence à un type non défini.  
  
 L’exemple suivant génère C2027.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```
