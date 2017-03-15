---
title: "log, logf, log10, log10f | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "log10f"
  - "logf"
  - "log10"
  - "log"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "logf"
  - "_log10l"
  - "log"
  - "_logl"
  - "log10f"
  - "log10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "calculer des logarithmes"
  - "log10f (fonction)"
  - "log10 (fonction)"
  - "log (fonction)"
  - "logf (fonction)"
  - "logarithmes"
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# log, logf, log10, log10f
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule des logarithmes.  
  
## Syntaxe  
  
```  
  
      double log(  
   double x   
);  
float log(  
   float x  
);  // C++ only  
long double log(  
   long double x  
);  // C++ only  
float logf(  
   float x   
);  
double log10(  
   double x  
);  
float log10(  
   float x  
);  // C++ only  
long double log10(  
   long double x  
);  // C++ only  
float log10f (  
   float x  
);  
```  
  
#### Paramètres  
 *x*  
 Valeur dont le logarithme doit être trouvé.  
  
## Valeur de retour  
 Les fonctions **log** retournent le logarithme népérien \(base e\) de *x* en cas de réussite.  Les fonctions log10 retournent le logarithme de base 10.  Si *x* est négatif, ces fonctions retournent un indéfini, par défaut.  Si *x* est 0, elles retournent INF \(infini\).  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± QNAN,IND|aucun|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
|x \< 0|NON VALIDE|\_DOMAIN|  
  
 **log** et `log10` a une implémentation qui utilise les extensions Streaming SIMD 2 \(SSE2\).  Voir le [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour des informations ainsi que connaitre l'état des restrictions sur l'usage de l'implémentation SSE2.  
  
## Notes  
 Comme C\+\+ permet une surcharge, vous pouvez appeler des surcharges de **log** et `log10`.  Dans un programme C, **log** et `log10` prennent et retournent toujours un double .  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**log**, `logf`, `log10`, `log10f`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_log.c  
/* This program uses log and log10  
 * to calculate the natural logarithm and  
 * the base-10 logarithm of 9,000.  
 */  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 9000.0;  
   double y;  
  
   y = log( x );  
   printf( "log( %.2f ) = %f\n", x, y );  
   y = log10( x );  
   printf( "log10( %.2f ) = %f\n", x, y );  
}  
```  
  
## Sortie  
  
```  
log( 9000.00 ) = 9.104980  
log10( 9000.00 ) = 3.954243  
```  
  
 Pour générer des logarithmes d'autres bases, utilisez la relation mathématique : log base b de a \=\= log naturel \(a\) \/ log naturel \(b\).  
  
```  
// logbase.cpp  
#include <math.h>  
#include <stdio.h>  
  
double logbase(double a, double base)  
{  
   return log(a) / log(base);  
}  
  
int main()  
{  
   double x = 65536;  
   double result;  
  
   result = logbase(x, 2);  
   printf("Log base 2 of %lf is %lf\n", x, result);  
}  
```  
  
## Sortie  
  
```  
Log base 2 of 65536.000000 is 16.000000  
```  
  
## Équivalent .NET Framework  
  
-   [System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx)  
  
-   [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [\_CIlog](../../c-runtime-library/cilog.md)   
 [\_CIlog10](../../c-runtime-library/cilog10.md)