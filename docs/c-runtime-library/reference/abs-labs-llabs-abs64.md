---
title: "ABS, laboratoires, llabs, _abs64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "abs"
  - "_abs64"
  - "labs"
  - "llabs"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "stdlib/_abs64"
  - "math/abs"
  - "_abs64"
  - "abs"
  - "labs"
  - "math/labs"
  - "llabs"
  - "math/llabs"
  - "cmath/abs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "valeurs absolues"
  - "abs (fonction)"
  - "abs64 (fonction)"
  - "_abs64 (fonction)"
  - "calculer des valeurs absolues"
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ABS, laboratoires, llabs, _abs64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la valeur absolue de l’argument.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `n`  
 Valeur numérique.  
  
## Valeur de retour  
 Le `abs`, `labs`, `llabs` et `_abs64` fonctions renvoient la valeur absolue du paramètre `n`. Aucun retour d'erreur.  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `abs` qui acceptent et retournent `long`, `long long`, `float`, `double`, et `long double` valeurs. Ces surcharges sont définis dans l’en\-tête \< cmath \>. Dans un programme C, `abs` toujours prend et retourne un entier.  
  
 **Section spécifique à Microsoft**  
  
 Étant donné que la plage d’entiers négatifs qui peuvent être représentées à l’aide de n’importe quel type intégral est supérieure à la plage d’entiers positifs qui peuvent être représentées à l’aide de ce type, il est possible de fournir un argument à ces fonctions ne peuvent pas être convertis. Si la valeur absolue de l’argument ne peut pas être représentée par le type de retour, le `abs` fonctions renvoient la valeur d’argument inchangée. Plus précisément, `abs(INT_MIN)` renvoie `INT_MIN`, `labs(LONG_MIN)` renvoie `LONG_MIN`, `llabs(LLONG_MIN)` renvoie `LLONG_MIN`, et `_abs64(_I64_MIN)` renvoie `_I64_MIN`. Cela signifie que le `abs` fonctions ne peuvent pas être utilisées pour garantir une valeur positive.  
  
 **Fin de la section spécifique à Microsoft**  
  
## Configuration requise  
  
|Routine|En\-tête C requis|En\-tête C\+\+ requis|  
|-------------|-----------------------|---------------------------|  
|`abs`, `labs`, `llabs`|\< math.h \> ou \< stdlib.h \>|\< cmath \>, \< cstdlib \>, \< stdlib.h \> ou \< math.h \>|  
|`_abs64`|\<stdlib.h\>|\< cstdlib \> ou \< stdlib.h \>|  
  
 Pour utiliser des versions surchargées de `abs` en C\+\+, vous devez inclure l’en\-tête \< cmath \>.  
  
## Exemple  
 Ce programme calcule et affiche les valeurs absolues de plusieurs nombres.  
  
```c  
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
La valeur absolue de -4 est la valeur absolue de-41567 est 41567, la valeur absolue de-9876543210 est 9876543210 est la valeur absolue de 0xffffffffffffffff de 4 résultats de spécifique à l’implémentation Microsoft de 0 x 0000000000000001 : abs(INT_MIN) retourne -2147483648 labs(LONG_MIN) retourne -2147483648 llabs(LLONG_MIN) retourne -9223372036854775808 _abs64(_I64_MIN) retourne 0 x 8000000000000000  
  
```  
  
## Équivalent .NET Framework  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../../c-runtime-library/reference/imaxabs.md)