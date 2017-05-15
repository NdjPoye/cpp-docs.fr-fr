---
title: EXP, expf, expl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
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
ms.openlocfilehash: bce9249134b9d0e3716d8b79a0bc0642c64fc5e6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="exp-expf-expl"></a>EXP, expf, expl
Calcule la valeur exponentielle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
long double expl(  
   long double x  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `x`  
 La virgule flottante valeur Elever à la puissance la base du logarithme népérien *e* par.  
  
## <a name="return-value"></a>Valeur de retour  
 Le `exp` fonctions retournent la valeur exponentielle du paramètre à virgule flottante, *x*, en cas de réussite. Autrement dit, le résultat est *e*<sup>*x*</sup>, où *e* est la base du logarithme népérien. De dépassement de capacité, la fonction retourne INF (infini) et de dépassement de capacité négatif, `exp` retourne 0.  
  
|Entrée|Exception SEH|Exception{b> <b}Matherr|  
|-----------|-------------------|-----------------------|  
|± Valeur NaN silencieuse, indéterminé|Aucune|_DOMAIN|  
|Nombre infini de ±|INVALID|_DOMAIN|  
|x ≥ 7,097827e+002|INEXACT+OVERFLOW|OVERFLOW|  
|X ≤ -7,083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|  
  
 Le `exp` possède une implémentation qui utilise des Extensions Streaming SIMD 2 (SSE2). Consultez [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour plus d’informations sur l’utilisation de l’implémentation SSE2 et sur les restrictions qui s’y rattachent.  
  
## <a name="remarks"></a>Remarques  
 C++ autorise la surcharge, vous pouvez appeler des surcharges de `exp` qui prennent un **float** ou **long double** argument. Dans un programme C, `exp` accepte et retourne toujours un **double**.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C requis|En-tête C++ requis|  
|--------------|---------------------|---|  
|`exp`, `expf`|\<math.h>|\<cmath> ou \<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
exp( 2.302585 ) = 10.000000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)
