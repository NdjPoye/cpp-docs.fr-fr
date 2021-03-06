---
title: Compilateur avertissement (niveau 1) C4669 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4669
dev_langs:
- C++
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baffb413a5c07acaeea7f4706ab9d6e951c65f04
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4669"></a>Avertissement du compilateur (niveau 1) C4669
'cast' : conversion risquée : 'classe' est un objet de type managé ou WinRT  
  
 Un cast contient un type managé ou Windows Runtime. Le compilateur termine le cast en effectuant une copie bit par bit d'un pointeur vers l'autre, mais ne fournit aucune autre vérification. Pour résoudre cet avertissement, n'effectuez pas de cast des classes qui contiennent des membres managés ou des types Windows Runtime.  
  
 L'exemple suivant génère l'avertissement C4669 et montre comment le corriger :  
  
```  
// C4669.cpp  
// compile with: /clr /W1  
ref struct A {  
   int i;  
   Object ^ pObj;   // remove the managed member to fix the warning  
};  
  
ref struct B {  
   int j;  
};  
  
int main() {  
   A ^ a = gcnew A;  
   B ^ b = reinterpret_cast<B ^>(a);   // C4669  
}  
```