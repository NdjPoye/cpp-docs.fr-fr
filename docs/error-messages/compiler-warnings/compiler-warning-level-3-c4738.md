---
title: Avertissement (niveau 3) du compilateur C4738 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ce2db890b7b90eedf5b4456e875a06f8f92b0289
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-warning-level-3-c4738"></a>Avertissement du compilateur (niveau 1) C4738
stockage de résultat flottant 32 bits en mémoire, perte possible de performances  
  
 L’erreur C4738 signale que le résultat d’une assignation, cast, passé argument ou autre opération peut devoir être arrondi ou que l’opération a manqué des registres et nécessaires à l’utilisation de mémoire (débordement). Cela peut entraîner une perte de performances.  
  
 Pour résoudre cet avertissement et éviter tout arrondi, compilez avec [Fast](../../build/reference/fp-specify-floating-point-behavior.md) ou utilisez `double` au lieu de `float`.  
  
 Pour résoudre cet avertissement et éviter de manquer de registres, modifier l’ordre de calcul et modifier votre utilisation d’incorporation (inlining)  
  
 Cet avertissement est désactivé par défaut. Pour plus d’informations, consultez [avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4738 :  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```
