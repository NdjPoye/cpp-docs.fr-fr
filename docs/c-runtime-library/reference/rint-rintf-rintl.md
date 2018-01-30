---
title: rint, rintf, rintl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- rintf
- rintl
- rint
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
- rintf
- rintl
- rint
dev_langs:
- C++
helpviewer_keywords:
- rintf function
- rint function
- rintl function
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90dcff78d7062e8f5735cf8622629682e330147b
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2018
---
# <a name="rint-rintf-rintl"></a>rint, rintf, rintl
Arrondit une valeur à virgule flottante à l'entier le plus proche dans un format à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double rint( double x );  
float rint( float x );  // C++ only  
long double rint( long double x );  // C++ only  
float rintf( float x );   
long double rintl( long double x );  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante à arrondir.  
  
## <a name="return-value"></a>Valeur de retour  
 Les fonctions `rint` retournent une valeur à virgule flottante qui représente l'entier le plus proche de `x`. Les valeurs médianes sont arrondies en fonction du paramètre actif du mode d'arrondi à virgule flottante, à l'instar des fonctions `nearbyint`. Contrairement aux fonctions `nearbyint`, les fonctions `rint` peuvent lever l'exception de virgule flottante `FE_INEXACT` si le résultat est différent de la valeur de l'argument. Aucun retour d'erreur.  
  
|Entrée|Exception SEH|Exception `_matherr`|  
|-----------|-------------------|--------------------------|  
|± ∞, QNAN, IND|aucun|aucun|  
|Nombres dénormalisés|EXCEPTION_FLT_UNDERFLOW|aucun|  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `rint` qui acceptent et retournent des valeurs `float` et `long double`. Dans un programme C, `rint` accepte et retourne toujours un `double`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`rint`, `rintf`, `rintl`|\<math.h>|\<cmath>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_rint.c  
// Build with: cl /W3 /Tc crt_rint.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 2.5 and -2.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 2.5;  
  
   printf("rint(%f) is %.0f\n", x, rint (x));  
   printf("rint(%f) is %.0f\n", -x, rint (-x));  
   printf("rintf(%f) is %.0f\n", y, rintf(y));  
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));  
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));  
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));  
}  
```  
  
```Output  
rint(2.499999) is 2  
rint(-2.499999) is -2  
rintf(2.800000) is 3  
rintf(-2.800000) is -3  
rintl(2.500000) is 3  
rintl(-2.500000) is -3  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)   
 [lround, lroundf, lroundl, llround, llroundf, llroundl](../../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)   
 [nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)   
 [rint](../../c-runtime-library/reference/rint-rintf-rintl.md)