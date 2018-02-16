---
title: pow, powf, powl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09b618e557fffadd3bfffb431fc7e89458c4f420
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="pow-powf-powl"></a>pow, powf, powl
Calcule `x` élevé à la puissance de `y`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Base.  
  
 `y`  
 Exposant.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de `x`<sup>y</sup>. Aucun message d’erreur n’est imprimé en cas de dépassement de capacité positif ou négatif.  
  
|Valeurs de x et y|Valeur de retour de pow|  
|-----------------------|-------------------------|  
|`x` \< > 0 et `y` = 0,0|1|  
|`x` = 0,0 et `y` = 0,0|1|  
|`x` = 0,0 et `y` < 0|INF|  
  
## <a name="remarks"></a>Notes  
 `pow` ne reconnaît pas les valeurs à virgule flottante intégrales supérieures à 2<sup>64</sup> (par exemple, `1.0E100`).  
  
 `pow` propose une implémentation qui utilise SSE2 (Streaming SIMD Extensions 2). Pour obtenir des informations sur l’utilisation de l’implémentation SSE2 et sur les restrictions qui s’y rattachent, consultez [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 Sachant que C++ autorise la surcharge, vous pouvez appeler l’une des diverses surcharges de `pow`. Dans un programme C, `pow` prend toujours deux valeurs doubles et en une.  
  
 La surcharge `pow(int, int)` n’est plus disponible. Si vous utilisez cette surcharge, le compilateur peut émettre C2668. Pour éviter ce problème, effectuez un cast du premier paramètre en `double`, `float` ou `long double`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`pow`, `powf`, `powl`|\<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [exp, expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [_CIpow](../../c-runtime-library/cipow.md)