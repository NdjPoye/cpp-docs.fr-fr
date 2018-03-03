---
title: Compilateur avertissement (niveau 1) C4382 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b0cef09795553759487e28ef61babe75b35ce03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4382"></a>Avertissement du compilateur (niveau 1) C4382
levée de 'type' : un type avec le constructeur de copie ou le destructeur __clrcall ne peut être intercepté que dans/CLR : pure module  
  
 Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 Lors de la compilation avec **/CLR** (pas **/CLR : pure**), la gestion des exceptions attend les fonctions membres dans un type natif soient [__cdecl](../../cpp/cdecl.md) et non [__clrcall](../../cpp/clrcall.md). Les types natifs avec des fonctions de membre à l’aide de `__clrcall` convention d’appel ne peut pas être interceptée dans un module compilé avec **/CLR**.  
  
 Si l’exception est interceptée dans un module compilé avec **/CLR : pure**, vous pouvez ignorer cet avertissement.  
  
 Pour plus d’informations, consultez l’article [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4382.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```