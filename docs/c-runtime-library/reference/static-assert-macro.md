---
title: _STATIC_ASSERT, macro | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _STATIC_ASSERT
dev_langs:
- C++
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 265796cdebbed1c0a067c44bbe6b71077be44a2b
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="staticassert-macro"></a>_STATIC_ASSERT, macro
Évalue une expression au moment de la compilation et génère une erreur quand le résultat est `FALSE`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `booleanExpression`  
 Expression (pointeurs inclus) qui prend une valeur différente de zéro (`TRUE`) ou 0 (`FALSE`).  
  
## <a name="remarks"></a>Notes  
 Cette macro ressemble aux [macros ASSERT et _ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), à ceci près que `booleanExpression` est évalué non pas au moment de l’exécution, mais au moment de la compilation. Si `booleanExpression` a la valeur `FALSE` (0), l’[erreur du compilateur C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) est générée.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, nous vérifions si la valeur de `sizeof` d’un `int` représente 2 octets ou plus et si la valeur de `sizeof` d’un `long` représente 1 octet. Le programme ne se compilera pas et générera une [erreur du compilateur C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md), car un `long` a une valeur qui représente plus de 1 octet.  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Macro|En-tête requis|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR, macros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)
