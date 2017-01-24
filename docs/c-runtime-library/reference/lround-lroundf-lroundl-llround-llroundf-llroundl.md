---
title: "lround, lroundf, lroundl, llround, llroundf, llroundl | Microsoft Docs"
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
  - "llround"
  - "llroundf"
  - "llroundl"
  - "lroundf"
  - "lround"
  - "lroundl"
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
  - "lround"
  - "lroundl"
  - "llroundl"
  - "llround"
  - "lroundf"
  - "llroundf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "llround (fonction)"
  - "llroundf (fonction)"
  - "llroundl (fonction)"
  - "lround (fonction)"
  - "lroundf (fonction)"
  - "lroundl (fonction)"
ms.assetid: cfb88a35-54c6-469f-85af-f7d695dcfdd8
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# lround, lroundf, lroundl, llround, llroundf, llroundl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Arrondit une valeur à virgule flottante à l'entier le plus proche.  
  
## Syntaxe  
  
```  
long lround(   
   double x   
);  
long lround(  
   float x  
);  // C++ only  
long lround(  
   long double x  
);  // C++ only  
long lroundf(  
   float x  
);  
long lroundl(  
   long double x  
);  
long long llround(   
   double x   
);  
long long llround(  
   float x  
);  // C++ only  
long long llround(  
   long double x  
);  // C++ only  
long long llroundf(  
   float x  
);  
long long llroundl(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante à arrondir.  
  
## Valeur de retour  
 Les fonctions `lround` et `llround` retournent l'entier `long` ou `long long` le plus proche de `x`.  Les valeurs à moitié sont arrondies en s'éloignant de zéro, indépendamment du paramètre du mode d'arrondi à virgule flottante.  Aucun retour d'erreur.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± `QNAN`, `IND`|aucun|`_DOMAIN`|  
  
## Notes  
 Comme C\+\+ permet la surcharge, vous pouvez appeler les surcharges de `lround` ou `llround` qui acceptent et retournent les valeurs `float` et `long double` .  Dans un programme C, `lround` et `llround` prennent et retournent toujours `double`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`lround`, `lroundf`, `lroundl`, `llround`, `llroundf`, `llroundl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_lround.c  
// Build with: cl /W3 /Tc crt_lround.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 3.5 and -3.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 3.5;  
  
   printf("lround(%f) is %d\n", x, lround(x));  
   printf("lround(%f) is %d\n", -x, lround(-x));  
   printf("lroundf(%f) is %d\n", y, lroundf(y));  
   printf("lroundf(%f) is %d\n", -y, lroundf(-y));  
   printf("lroundl(%Lf) is %d\n", z, lroundl(z));  
   printf("lroundl(%Lf) is %d\n", -z, lroundl(-z));  
}  
```  
  
  **lround\(2.499999\) est 2**  
**lround\(\-2.499999\) est \-2**  
**lroundf\(2.800000\) est 3**  
**lroundf\(\-2.800000\) est \-3**  
**lroundl\(2.500000\) est 4**  
**lroundl\(\-2.500000\) est \-4**   
## Équivalent .NET Framework  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](http://msdn.microsoft.com/fr-fr/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [nearbyint, nearbyintf, nearbyintl](http://msdn.microsoft.com/fr-fr/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)