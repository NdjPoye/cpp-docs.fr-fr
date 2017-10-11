---
title: Erreur du compilateur C2653 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cc7990614283a20e9d07f52187258dbccad7c075
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2653"></a>Erreur du compilateur C2653
'identificateur' : n’est pas un nom de classe ou espace de noms  
  
Syntaxe requiert un nom de classe, structure, union ou espace de noms.  
  
L’exemple suivant génère l’erreur C2653 :  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 est également possible si vous essayez de définir un *espace de noms composé*, un espace de noms qui contient un ou plusieurs noms d’espace de noms imbriqué à l’étendue, lorsque vous utilisez une version de Visual C++ avant Visual Studio 2015 Update 3. Compound, espace de noms définitions ne sont pas autorisées en C++ avant C ++ 17. À partir de Visual C++ 2015 Update 3, le compilateur prend en charge les définitions de l’espace de noms composé lorsque le [/std : c ++ dernière](../../build/reference/std-specify-language-standard-version.md) option du compilateur est spécifiée :  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++latest to fix.
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  
