---
title: "continuer d’instruction (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 502254adc8b01966182f911af5a0dce8af36c1f3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="continue-statement-c"></a>continue, instruction (C++)
Force le transfert de contrôle à l’expression de contrôle de la plus petite [faire](../cpp/do-while-statement-cpp.md), [pour](../cpp/for-statement-cpp.md), ou [tandis que](../cpp/while-statement-cpp.md) boucle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Remarques  
 Toutes les instructions restantes dans l'itération actuelle ne sont pas exécutées. L'itération suivante de la boucle est déterminée comme suit :  
  
-   Dans une boucle `do` ou `while`, l'itération suivante démarre en réévaluant l'expression de contrôle de l'instruction `do` ou `while`.  
  
-   Dans une boucle `for` (utilisant la syntaxe `for`(`init-expr`; `cond-expr`; `loop-expr`)), la clause `loop-expr` est exécutée. Ensuite la clause `cond-expr` est réévaluée et, selon le résultat, la boucle se termine ou une autre itération a lieu.  
  
 L'exemple suivant montre comment l'instruction `continue` peut être utilisée pour ignorer les sections de code et démarrer l'itération suivante d'une boucle.  
  
## <a name="example"></a>Exemple  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
```Output  
before the continue  
before the continue  
before the continue  
after the do loop  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)
