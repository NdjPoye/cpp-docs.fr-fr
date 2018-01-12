---
title: Erreur du compilateur C2975 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2975
dev_langs: C++
helpviewer_keywords: C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f779ec2623b6b07f61c1e8347304288d0bcfe96a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2975"></a>Erreur du compilateur C2975

> '*argument*' : argument template non valide pour '*type*', expression constante de compilation attendue

L’argument de modèle ne correspond pas à la déclaration de modèle ; une expression constante doit apparaître entre crochets pointus. Les variables ne sont pas autorisées en tant qu’arguments réels du modèle. Vérifiez la définition du modèle pour trouver les types corrects.

## <a name="example"></a>Exemple

L’exemple suivant génère l’erreur C2975 s’et montre également l’utilisation correcte :

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 se produit également lorsque vous utilisez &#95; &#95; LIGNE &#95; &#95; comme une constante de compilation avec [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md). Une solution consisterait à compiler avec [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) au lieu de **/Zi**.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```