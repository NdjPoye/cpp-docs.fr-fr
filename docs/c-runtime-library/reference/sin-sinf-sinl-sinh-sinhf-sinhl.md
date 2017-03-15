---
title: "sin, sinf, sinl, sinh, sinhf, sinhl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "sinl"
  - "sinf"
  - "sinhf"
  - "sinh"
  - "sin"
  - "sinhl"
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
  - "_sinl"
  - "sinf"
  - "sinhl"
  - "sinl"
  - "sin"
  - "sinhf"
  - "_sinhl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sinhl (fonction)"
  - "_sinl (fonction)"
  - "calculer les sinus"
  - "fonctions hyperboliques"
  - "sin (fonction)"
  - "sinf (fonction)"
  - "sinh (fonction)"
  - "sinhf (fonction)"
  - "sinhl (fonction)"
  - "sinl (fonction)"
  - "fonctions trigonométriques"
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# sin, sinf, sinl, sinh, sinhf, sinhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule les sinus et les sinus hyperboliques.  
  
## Syntaxe  
  
```  
double sin(  
   double x   
);  
float sin(  
   float x  
);  // C++ only  
long double sin(  
   long double x  
);  // C++ only  
float sinf(  
   float x   
);  
long double sinl(  
   long double x  
);  
double sinh(  
   double x   
);  
float sinh(  
   float x   
);  // C++ only  
long double sinh(  
   long double x  
);  // C++ only  
float sinhf(  
   float x  
);  
long double sinhl(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 Angle en radians.  
  
## Valeur de retour  
 Les fonctions `sin` renvoient le sinus de `x`.  Si `x` est supérieure ou égale à 263, ou inférieure ou égale à – 263, une perte d'importance dans le résultat se produit.  
  
 Les fonctions `sinh` renvoient le sinus hyperbolique de `x`.  Par défaut, si le résultat est trop important, `errno` assigne `sinh` à `ERANGE` et renvoie ±`HUGE_VAL`.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± QNAN,IND|Aucun|\_DOMAIN|  
|± ∞ \(sin, sinf, sinl\)|NON VALIDE|\_DOMAIN|  
|&#124;x&#124; ≥ 7.104760e\+002 \(sinh, sinhf, sinhl\)|OVERFLOW\+INEXACT|Dépassement de capacité.|  
  
 Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Comme C\+\+ permet la surcharge, vous pouvez appeler les surcharges de `sin` ou `sinh` qui acceptent et renvoient les valeurs `float` et `long double` .  Dans un programme C, `sin` et `sinh` prennent et renvoient toujours `double`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`sin`, `sinf`, `sinl`, `sinh`, `sinhf`, `sinhl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_sincos.c  
// This program displays the sine, hyperbolic  
// sine, cosine, and hyperbolic cosine of pi / 2.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
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
  
  **sin\( 1.570796 \) \= 1.000000**  
**sinh\( 1.570796 \) \= 2.301299**  
**cos\( 1.570796 \) \= 0.000000**  
**cosh\( 1.570796 \) \= 2.509178**   
## Équivalent .NET Framework  
  
-   [System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx)  
  
-   [System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIsin](../../c-runtime-library/cisin.md)