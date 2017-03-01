---
title: Erreur du compilateur C2653 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 2203cf8a09dbb05f6145ed238ab9fc03e458aaa5
ms.lasthandoff: 02/24/2017

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
  
C2653 est également possible si vous essayez de définir un *espace de noms composé*, un espace de noms qui contient un ou plusieurs noms d’espace de noms étendue imbriquée, lorsque vous utilisez une version de Visual C++ avant Visual Studio 2015 Update 3. Composés d’espace de noms définitions ne sont pas autorisées en C++ avant C ++&17;. À partir de Visual C++ 2015 Update 3, le compilateur prend en charge les définitions d’espace de noms composés lors de la [/std:c ++ dernières](../../build/reference/std-specify-language-standard-version.md) option du compilateur est spécifiée :  
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
