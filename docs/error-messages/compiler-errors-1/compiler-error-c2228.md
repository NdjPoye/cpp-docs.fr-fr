---
title: Erreur du compilateur C2228 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 39bbed326de5fc0a367e9b7693d3975b766e9bfc
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2228"></a>Erreur du compilateur C2228
la partie gauche de '.identifier' doit avoir un class/struct/union  
  
 L’opérande à gauche de l’opérateur point (.) n’est pas une classe, structure ou union.  
  
 L’exemple suivant génère l’erreur C2228 :  
  
```  
// C2228.cpp  
int i;  
struct S {  
public:  
    int member;  
} s, *ps = &s;  
  
int main() {  
   i.member = 0;   // C2228 i is not a class type  
   ps.member = 0;  // C2228 ps is a pointer to a structure  
  
   s.member = 0;   // s is a structure type  
   ps->member = 0; // ps points to a structure S  
}  
```  
  
 Vous recevez également cette erreur si vous utilisez une syntaxe incorrecte lors de l’utilisation des Extensions managées. Si vous pouvez utiliser l’opérateur point pour accéder au membre d’une classe managée dans d’autres langages de Visual Studio, un pointeur vers l’objet en C++ signifie que vous devez utiliser l’opérateur -> pour accéder au membre :  
  
 Problème :`String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 Oui :`String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
