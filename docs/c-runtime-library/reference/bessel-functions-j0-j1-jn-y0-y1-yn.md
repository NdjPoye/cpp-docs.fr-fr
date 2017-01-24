---
title: "Fonctions de Bessel&#160;: _j0, _j1, _jn, _y0, _y1, _yn | Microsoft Docs"
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
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
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
  - "c.bessel"
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Fonctions de Bessel"
  - "_j0 (fonction)"
  - "_j1 (fonction)"
  - "_jn (fonction)"
  - "_y0 (fonction)"
  - "_y1 (fonction)"
  - "_yn (fonction)"
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctions de Bessel&#160;: _j0, _j1, _jn, _y0, _y1, _yn
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la fonction de Bessel de première ou deuxième espèce, d’ordre 0, 1 ou n. Lesfonctions de Bessel sont couramment utilisées dans les calculs mathématiques de la théorie sur les ondes électromagnétiques.  
  
## Syntaxe  
  
```  
double _j0(   
   double x   
);  
double _j1(   
   double x   
);  
double _jn(   
   int n,  
   double x   
);  
double _y0(   
   double x   
);  
double _y1(   
   double x   
);  
double _yn(   
   int n,  
   double x   
);  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
 `n`  
 Ordre d’entier de la fonction de Bessel.  
  
## Valeur de retour  
 Chacune de ces routines retourne une fonction de Bessel de `x`. Si `x` est négatif dans la fonction `_y0`, `_y1` ou `_yn`, la routine affecte la valeur `EDOM` à `errno`, affiche un message d’erreur `_DOMAIN` dans `stderr`, et retourne `_HUGE_VAL`. Vous pouvez modifier la gestion des erreurs à l’aide de `_matherr`.  
  
## Notes  
 Les routines `_j0`, `_j1` et `_jn` retournent des fonctions de Bessel de première espèce : respectivement d’ordre 0, 1 et n.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
  
 Les routines `_y0`, `_y1` et `_yn` retournent des fonctions de Bessel de deuxième espèce : respectivement d’ordre 0, 1 et n.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
|± 0|`ZERODIVIDE`|`_SING`|  
|&#124;x&#124;\<0.0|`INVALID`|`_DOMAIN`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|\<cmath\> \(C\+\+\), \<math.h\> \(C, C\+\+\)|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_bessel1.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.387;  
   int n = 3, c;  
  
   printf( "Bessel functions for x = %f:\n", x );  
   printf( " Kind   Order  Function     Result\n\n" );  
   printf( " First  0      _j0( x )     %f\n", _j0( x ) );  
   printf( " First  1      _j1( x )     %f\n", _j1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );  
   printf( " Second 0      _y0( x )     %f\n", _y0( x ) );  
   printf( " Second 1      _y1( x )     %f\n", _y1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );  
}  
```  
  
```Output  
Bessel functions for x = 2.387000: Kind   Order  Function     Result First  0      _j0( x )     0.009288 First  1      _j1( x )     0.522941 First  2      _jn( 2, x )  0.428870 First  3      _jn( 3, x )  0.195734 First  4      _jn( 4, x )  0.063131 Second 0      _y0( x )     0.511681 Second 1      _y1( x )     0.094374 Second 2      _yn( 2, x )  -0.432608 Second 3      _yn( 3, x )  -0.819314 Second 4      _yn( 4, x )  -1.626833  
```  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)