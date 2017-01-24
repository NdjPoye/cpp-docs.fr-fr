---
title: "_STATIC_ASSERT, macro | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_STATIC_ASSERT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_STATIC_ASSERT (macro)"
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _STATIC_ASSERT, macro
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Évalue une expression au moment de la compilation et génère une erreur lorsque le résultat est `FALSE`.  
  
## Syntaxe  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### Paramètres  
 `booleanExpression`  
 Expression \(pointeurs compris\) qui s'évalue à une valeur non nulle \(`TRUE`\) ou 0 \(`FALSE`\).  
  
## Notes  
 Cette macro ressemble à [macros de \_ASSERT et de \_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), sauf que `booleanExpression` est évaluée au moment de la compilation et non au moment de l'exécution.  Si `booleanExpression` prend la valeur `FALSE` \(0\), [Erreur du compilateur C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) est généré.  
  
## Exemple  
 Dans cet exemple, nous vérifions si la `sizeof` un `int` dépasse ou égale 2 octets et si la `sizeof` un `long` est de 1 octet.  Le programme ne compilera pas et il génèrera [Erreur du compilateur C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) car `long` est supérieur à 1 octets.  
  
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
  
## Configuration requise  
  
|Macro|En\-tête requis|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h\>|  
  
## Équivalent .NET Framework  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR \(macros\)](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)