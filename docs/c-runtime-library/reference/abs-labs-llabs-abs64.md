---
title: abs, labs, llabs, _abs64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- abs
- _abs64
- labs
- llabs
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
dev_langs: C++
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64c09dc8c8ce1ce5493ac4b2515c6b0be2910627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="abs-labs-llabs-abs64"></a>abs, labs, llabs, _abs64
Calcule la valeur absolue de l’argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int abs(   
   int n   
);  
long abs(   
   long n   
);   // C++ only  
long long abs(   
   long long n   
);   // C++ only  
double abs(   
   double n   
);   // C++ only  
long double abs(  
   long double n  
);   // C++ only  
float abs(  
   float n   
);   // C++ only  
long labs(  
   long n   
);  
long long llabs(  
   long long n   
);  
__int64 _abs64(   
   __int64 n   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `n`  
 Valeur numérique.  
  
## <a name="return-value"></a>Valeur de retour  
 Les fonctions `abs`, `labs`, `llabs` et `_abs64` retournent la valeur absolue du paramètre `n`. Aucun retour d'erreur.  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `abs` qui acceptent et retournent des valeurs `long`, `long long`, `float`, `double` et `long double`. Ces surcharges sont définies dans l’en-tête \<cmath>. Dans un programme C, `abs` accepte et retourne toujours un entier.  
  
 **Section spécifique à Microsoft**  
  
 Étant donné que la plage d’entiers négatifs qui peuvent être représentés à l’aide de n’importe quel type intégral est supérieure à la plage d’entiers positifs qui peuvent être représentés à l’aide de ce type, il est possible de fournir un argument à ces fonctions qui ne peut pas être converti. Si la valeur absolue de l’argument ne peut pas être représentée par le type de retour, les fonctions `abs` retournent la valeur d’argument inchangée. Plus précisément, `abs(INT_MIN)` retourne `INT_MIN`, `labs(LONG_MIN)` retourne `LONG_MIN`, `llabs(LLONG_MIN)` retourne `LLONG_MIN`, tandis que `_abs64(_I64_MIN)` retourne `_I64_MIN`. Cela signifie que les fonctions `abs` ne peuvent pas être utilisées pour garantir une valeur positive.  
  
 **Fin de la section spécifique à Microsoft**  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête C requis|En-tête C++ requis|  
|-------------|-----------------------|---------------------------|  
|`abs`, `labs`, `llabs`|\<math.h> ou \<stdlib.h>|\<cmath>, \<cstdlib>, \<stdlib.h> ou \<math.h>|  
|`_abs64`|\<stdlib.h>|\<cstdlib> ou \<stdlib.h>|  
  
 Pour utiliser les versions surchargées de `abs` en C++, vous devez inclure l’en-tête \<cmath>.  
  
## <a name="example"></a>Exemple  
 Ce programme calcule et affiche les valeurs absolues de plusieurs nombres.  
  
```C  
// crt_abs.c  
// Build: cl /W3 /TC crt_abs.c  
// This program demonstrates the use of the abs function  
// by computing and displaying the absolute values of  
// several numbers.  
  
#include <stdio.h>  
#include <math.h>  
#include <stdlib.h>  
#include <limits.h>  
  
int main( void )  
{  
    int ix = -4;  
    long lx = -41567L;  
    long long llx = -9876543210LL;  
    __int64 wx = -1;  
  
    // absolute 32 bit integer value  
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));  
  
    // absolute long integer value  
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));  
  
    // absolute long long integer value  
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));  
  
    // absolute 64 bit integer value  
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,   
        _abs64(wx));  
  
    // Integer error cases:  
    printf_s("Microsoft implementation-specific results:\n");  
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));  
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));  
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));  
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));  
}  
```  
  
```Output  
The absolute value of -4 is 4  
The absolute value of -41567 is 41567  
The absolute value of -9876543210 is 9876543210  
The absolute value of 0xffffffffffffffff is 0x0000000000000001  
Microsoft implementation-specific results:  
 abs(INT_MIN) returns -2147483648  
 labs(LONG_MIN) returns -2147483648  
 llabs(LLONG_MIN) returns -9223372036854775808  
 _abs64(_I64_MIN) returns 0x8000000000000000  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_cabs](../../c-runtime-library/reference/cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../../c-runtime-library/reference/imaxabs.md)