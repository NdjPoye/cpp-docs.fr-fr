---
title: continuer d’instruction (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b153c9f5dfae93f1a5cb83dc2b9bcfc09e77af07
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="continue-statement-c"></a>continue, instruction (C++)
Force le transfert de contrôle à l’expression de contrôle de la plus petite [faire](../cpp/do-while-statement-cpp.md), [pour](../cpp/for-statement-cpp.md), ou [tandis que](../cpp/while-statement-cpp.md) boucle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Notes  
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