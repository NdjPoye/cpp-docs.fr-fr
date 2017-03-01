---
title: exp, expf | Microsoft Docs
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
- exp
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- expf function
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f6fb2d2dc585633915587ff7b6e5cfbd69c4deb
ms.lasthandoff: 02/24/2017

---
# <a name="exp-expf"></a>exp, expf
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
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
## <a name="return-value"></a>Valeur de retour  
 La fonction `exp` retourne la valeur exponentielle du paramètre à virgule flottante, `x`, en cas de réussite. Autrement dit, le résultat est e à la puissance `x`, où e est la base du logarithme népérien. En cas de dépassement, la fonction retourne INF (infini), tandis qu’en cas de soupassement, `exp` retourne la valeur 0.  
  
|Entrée|Exception SEH|Exception{b> <b}Matherr|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|None|_DOMAIN|  
|± ∞|INVALID|_DOMAIN|  
|x ≥ 7,097827e+002|INEXACT+OVERFLOW|OVERFLOW|  
|X ≤ -7,083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|  
  
 `exp` présente une implémentation qui utilise SSE2 (Streaming SIMD Extensions 2). Consultez [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour plus d’informations sur l’utilisation de l’implémentation SSE2 et sur les restrictions qui s’y rattachent.  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `exp`. Dans un programme C, `exp` accepte et retourne toujours un double.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`exp`, `expf`|\<math.h>|  
  
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
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 [System::Math::Exp](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)
