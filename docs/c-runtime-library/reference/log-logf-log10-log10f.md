---
title: log, logf, log10, log10f | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- log10f
- logf
- log10
- log
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- logf
- _log10l
- log
- _logl
- log10f
- log10
dev_langs:
- C++
helpviewer_keywords:
- calculating logarithms
- log10f function
- log10 function
- log function
- logf function
- logarithms
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 22c41d6b2712954f05249192c3a5e386b8102554
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="log-logf-log10-log10f"></a>log, logf, log10, log10f
Calcule le logarithme.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 *x*  
 Valeur dont le logarithme doit être recherché.  
  
## <a name="return-value"></a>Valeur de retour  
 Les fonctions **log** retournent le logarithme népérien (base e) de *x* en cas de réussite. Les fonctions log10 retournent un logarithme en base 10. Si *x* est négatif, ces fonctions retournent un indéfini, par défaut. Si *x* est égal à 0, elles retournent INF (infini).  
  
|Entrée|Exception SEH|Exception{b> <b}Matherr|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|aucun|_DOMAIN|  
|± 0|ZERODIVIDE|_SING|  
|x < 0|INVALID|_DOMAIN|  
  
 **log** et `log10` présentent une implémentation qui utilise SSE2 (Streaming SIMD Extensions 2). Consultez [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour plus d’informations sur l’utilisation de l’implémentation SSE2 et sur les restrictions qui s’y rattachent.  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de **log** et `log10`. Dans un programme C, **log** et `log10` acceptent et retournent toujours un double.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|**log**, `logf`, `log10`, `log10f`|\<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="output"></a>Sortie  
  
```  
log( 9000.00 ) = 9.104980  
log10( 9000.00 ) = 3.954243  
```  
  
 Pour générer le logarithme pour d’autres bases, utilisez la relation mathématique : log base b de a == logarithme népérien (a) / logarithme népérien (b).  
  
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
  
## <a name="output"></a>Sortie  
  
```  
Log base 2 of 65536.000000 is 16.000000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [EXP, expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [_CIlog](../../c-runtime-library/cilog.md)   
 [_CIlog10](../../c-runtime-library/cilog10.md)
