---
title: "rint, rintf, rintl | Microsoft Docs"
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
  - "rintf"
  - "rintl"
  - "rint"
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
  - "rintf"
  - "rintl"
  - "rint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rintf, fonction"
  - "rint, fonction"
  - "rintl, fonction"
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rint, rintf, rintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Arrondit une valeur à virgule flottante à l'entier le plus proche dans un format à virgule flottante.  
  
## Syntaxe  
  
```  
double rint( double x ); float rint( float x );  // C++ only long double rint( long double x );  // C++ only float rintf( float x );  long double rintl( long double x );    
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante à arrondir.  
  
## Valeur de retour  
 Les fonctions `rint` retournent une valeur à virgule flottante qui représente l'entier le plus proche de `x`.  Les valeurs médianes sont arrondies en fonction du paramètre actif du mode d'arrondi à virgule flottante, à l'instar des fonctions `nearbyint`.  Contrairement aux fonctions `nearbyint`, les fonctions `rint` peuvent lever l'exception de virgule flottante `FE_INEXACT` si le résultat est différent de la valeur de l'argument.  Aucun retour d'erreur.  
  
|Entrée|Exception SEH|Exception `_matherr`|  
|------------|-------------------|--------------------------|  
|± ∞, QNAN, IND|aucun|aucun|  
|Nombres dénormalisés|EXCEPTION\_FLT\_UNDERFLOW|aucun|  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `rint` qui acceptent et retournent des valeurs `float` et `long double`.  Dans un programme C, `rint` accepte et retourne toujours un `double`.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`rint`, `rintf`, `rintl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
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
  
  **rint\(2,499999\) est égal à 2**  
**rint\(\-2,499999\) est égal à \-2**  
**rintf\(2,800000\) est égal à 3**  
**rintf\(\-2,800000\) est égal à \-3**  
**rintl\(2,500000\) est égal à 3**  
**rintl\(\-2,500000\) est égal à \-3**   
## Équivalent .NET Framework  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](http://msdn.microsoft.com/fr-fr/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [lround, lroundf, lroundl, llround, llroundf, llroundl](../../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)   
 [nearbyint, nearbyintf, nearbyintl](http://msdn.microsoft.com/fr-fr/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint](../../c-runtime-library/reference/rint-rintf-rintl.md)