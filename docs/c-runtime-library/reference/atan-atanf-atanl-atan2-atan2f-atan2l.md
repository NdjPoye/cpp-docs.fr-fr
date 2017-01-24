---
title: "atan, atanf, atanl, atan2, atan2f, atan2l | Microsoft Docs"
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
  - "atan2f"
  - "atan2l"
  - "atan2"
  - "atanf"
  - "atan"
  - "atanl"
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
  - "atan"
  - "atan2l"
  - "atan2"
  - "atanl"
  - "atanf"
  - "atan2f"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "arctangent (fonction)"
  - "atan (fonction)"
  - "atan2 (fonction)"
  - "atan2f (fonction)"
  - "atan2l (fonction)"
  - "atanf (fonction)"
  - "atanl (fonction)"
  - "fonctions trigonométriques"
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atan, atanf, atanl, atan2, atan2f, atan2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule l'arctangente de `x` \(`atan`, `atanf`, et `atanl`\) ou l'arctangente de `y`\/`x` \(`atan2`, `atan2f`, et `atan2l`\).  
  
## Syntaxe  
  
```  
double atan(   
   double x   
);  
float atan(  
   float x   
);  // C++ only  
long double atan(  
   long double x  
);  // C++ only  
double atan2(   
   double y,   
   double x   
);  
float atan2(  
   float y,  
   float x  
);  // C++ only  
long double atan2(  
   long double y,  
   long double x  
);  // C++ only  
float atanf(   
   float x   
);  
long double atanl(  
   long double x  
);  
float atan2f(  
   float y,  
   float x  
);  
long double atan2l(  
   long double y,  
   long double x  
);  
```  
  
#### Paramètres  
 `x`, `y`  
 Nombres quelconques.  
  
## Valeur de retour  
 `atan` retourne l'arctangente de `x` dans la plage – π\/2 à π\/2 radians.  `atan2` retourne l'arctangente de `y/x` dans la plage – π à π radians.  Si `x` est égal à 0, `atan`, renvoie 0 .  Si les deux paramètres de `atan2` sont 0, la fonction renvoie 0.  Tous les résultats sont en radians.  
  
 `atan2` utilise les signes des deux paramètres pour déterminer le quadrant de la valeur retournée.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|aucun|`_DOMAIN`|  
  
## Notes  
 La fonction `atan` calcule arctangente \(la fonction inverse de la tangente\) de `x`.  `atan2` calcule l'arctangente de `y`\/`x` \(si `x` est égal à 0, `atan2` retourne π\/2 si `y` est positif, \- π\/2 si `y` est négatif, ou nul si `y` est égal à 0.\)  
  
 `atan` a une implémentation qui utilise les extensions Streaming SIMD 2 \(SSE2\).  Pour plus d'informations et de restrictions sur l'utilisation de l'implémentation SSE2, consultez [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 Comme C\+\+ permet une surcharge, vous pouvez appeler des surcharges de `atan` et `atan2`.  Dans un programme C, `atan` et `atan2` prennent et retournent toujours des doubles.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`atan`, `atan2`, `atanf`, `atan2f`, `atanl`, `atan2l`|\<math.h\>|  
  
## Exemple  
  
```  
// crt_atan.c  
// arguments: 5 0.5  
#include <math.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( int ac, char* av[] )   
{  
   double x, y, theta;  
   if( ac != 3 ){  
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );  
      return 1;  
   }  
   x = atof( av[1] );  
   theta = atan( x );  
   printf( "Arctangent of %f: %f\n", x, theta );  
   y = atof( av[2] );  
   theta = atan2( y, x );  
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );   
   return 0;  
}  
```  
  
  **Arctangente de 5,000000 : 1,373401**  
**Arctangente de 0.500000 \/ 5.000000 : 0.099669**   
## Équivalent .NET Framework  
  
-   [System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx)  
  
-   [System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIatan](../../c-runtime-library/ciatan.md)   
 [\_CIatan2](../../c-runtime-library/ciatan2.md)