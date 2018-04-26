---
title: sin, sinf, sinl, sinh, sinhf, sinhl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- sinl
- sinf
- sinhf
- sinh
- sin
- sinhl
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
- _sinl
- sinf
- sinhl
- sinl
- sin
- sinhf
- _sinhl
dev_langs:
- C++
helpviewer_keywords:
- sinh function
- _sinl function
- _sinhl function
- sinhf function
- sinl function
- calculating sines
- sin function
- trigonometric functions
- sinf function
- sinhl function
- hyperbolic functions
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54718553d71a498463dbc881da8ceb3401ff5b5b
ms.sourcegitcommit: 9a3a3d59176043ae60584482c2572c07f757b320
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2018
---
# <a name="sin-sinf-sinl-sinh-sinhf-sinhl"></a>sin, sinf, sinl, sinh, sinhf, sinhl
Calcule le sinus et le sinus hyperbolique.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
double sin(double x);
  
float sin(float x);  // C++ only 
 
long double sin(long double x);  // C++ only  

float sinf(float x);  

long double sinl(long double x);  

double sinh(double x);  

float sinh(float x);  // C++ only  

long double sinh(long double x);  // C++ only  

float sinhf(float x);  

long double sinhl(long double x);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Angle en radians.  
  
## <a name="return-value"></a>Valeur de retour  
 Les fonctions `sin` retournent le sinus de `x`. Si `x` est supérieur ou égal à 263 ou inférieur ou égal à -263, une perte de crédibilité du résultat se produit.  
  
 Les fonctions `sinh` retournent le sinus hyperbolique de `x`. Par défaut, si le résultat est trop volumineux, `sinh` définit `errno` à `ERANGE` et retourne ±`HUGE_VAL`.  
  
|Entrée|Exception SEH|Exception{b> <b}Matherr|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|Aucun|_DOMAIN|  
|± ∞ (sin, sinf, sinl)|INVALID|_DOMAIN|  
|&#124;x&#124; ≥ 7.104760e+002 (sinh, sinhf, sinhl)|OVERFLOW+INEXACT|OVERFLOW|  
  
 Pour plus d’informations sur les codes de retour, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Sachant que C++ autorise la surcharge, vous pouvez appeler des surcharges de `sin` et `sinh` qui acceptent et retournent des valeurs `float` ou `long double`. Dans un programme C, `sin` et `sinh` acceptent et retournent toujours un `double`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`sin`, `sinf`, `sinl`, `sinh`, `sinhf`, `sinhl`|\<math.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_sincos.c  
// This program displays the sine, hyperbolic  
// sine, cosine, and hyperbolic cosine of pi / 2.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void)  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = pi / 2;  
   y = sin( x );  
   printf( "sin( %f ) = %f\n", x, y );  
   y = sinh( x );  
   printf( "sinh( %f ) = %f\n",x, y );  
   y = cos( x );  
   printf( "cos( %f ) = %f\n", x, y );  
   y = cosh( x );  
   printf( "cosh( %f ) = %f\n",x, y );  
}  
```  
  
```Output  
sin( 1.570796 ) = 1.000000  
sinh( 1.570796 ) = 2.301299  
cos( 1.570796 ) = 0.000000  
cosh( 1.570796 ) = 2.509178  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CIsin](../../c-runtime-library/cisin.md)