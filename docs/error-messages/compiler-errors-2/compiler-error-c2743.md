---
title: Erreur du compilateur C2743 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7420231e64515b556cfe81fc695eda5f75231506
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2743"></a>Erreur du compilateur C2743
'type' : Impossible d’intercepter un type natif avec le destructeur __clrcall ou le constructeur de copie  
  
 Un module compilé avec **/clr** essayé d’intercepter une exception de type natif où le de type destructeur ou constructeur de copie utilise `__clrcall` convention d’appel.  
  
 Lorsque vous compilez avec **/clr**, la gestion des exceptions s’attend aux fonctions membres dans un type natif soient [__cdecl](../../cpp/cdecl.md) et non [__clrcall](../../cpp/clrcall.md). Les types natifs possédant des fonctions membres à l’aide de `__clrcall` convention d’appel ne peut pas être interceptée dans un module compilé avec **/clr**.  
  
 Pour plus d’informations, consultez l’article [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2743.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```
