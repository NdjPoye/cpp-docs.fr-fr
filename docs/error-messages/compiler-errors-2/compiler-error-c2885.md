---
title: Erreur du compilateur C2885 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98f3501cc029094d7f00e941026c0f7d1ed7d80b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2885"></a>Erreur du compilateur C2885
'classe::identificateur' : pas une valide à l’aide de déclaration au niveau de portée sans classe  
  
 Vous avez utilisé un [à l’aide de](../../cpp/using-declaration.md) déclaration de manière incorrecte.  
  
## <a name="example"></a>Exemple  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C++ 2005 : il n’est plus valide une `using` déclaration pour un type imbriqué ; vous devez explicitement qualifier chaque référence au type imbriqué, placer le type dans un nom l’espace, ou créer un typedef.  
  
 L’exemple suivant génère C2885.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## <a name="example"></a>Exemple  
 Si vous utilisez le `using` mot clé avec un membre de classe C++, vous devez définir ce membre à l’intérieur d’une autre classe (une classe dérivée).  
  
 L’exemple suivant génère C2885.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```