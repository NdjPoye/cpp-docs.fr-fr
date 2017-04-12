---
title: Compilateur avertissement (niveau 1) C4750 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
caps.latest.revision: 5
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
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 6e22ef89b92a5b584979abbd370f82b482cf74e0
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4750"></a>Avertissement du compilateur (niveau 1) C4750
'identifier' : fonction with _alloca() inline dans une boucle  
  
 La fonction 'identificateur' force l’expansion inline de la [_alloca](../../c-runtime-library/reference/alloca.md) fonction dans une boucle, ce qui peut entraîner un débordement de pile lors de la boucle est exécutée.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Assurez-vous que la fonction 'identificateur' n’est pas modifiée avec le [__forceinline](../../cpp/inline-functions-cpp.md) spécificateur.  
  
2.  Assurez-vous que la fonction 'identificateur' ne contient pas une [_alloca](../../c-runtime-library/reference/alloca.md) fonction contenue dans une boucle.  
  
3.  Ne spécifiez pas le [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [Og](../../build/reference/ox-full-optimization.md), ou [/Og](../../build/reference/og-global-optimizations.md) commutateur de compilation.  
  
4.  Place le [_alloca](../../c-runtime-library/reference/alloca.md) de fonction dans une [essayez-EXCEPT, instruction](../../cpp/try-except-statement.md) qui intercepte un débordement de pile.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant appelle `MyFunction` dans une boucle, et `MyFunction` appelle la fonction `_alloca` . Le modificateur `__forceinline` provoque l’expansion inline de la fonction `_alloca` .  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [_alloca](../../c-runtime-library/reference/alloca.md)
