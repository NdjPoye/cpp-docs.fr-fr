---
title: _STATIC_ASSERT, macro | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f62f2f2f5a0d78a0b77cb21d869be209d9293bd0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
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
  
## <a name="requirements"></a>Configuration requise  
  
|Macro|En-tête requis|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR, macros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)