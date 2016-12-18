---
title: "modf, modff, modfl | Microsoft Docs"
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
  - "modff"
  - "modf"
  - "modfl"
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
  - "modff"
  - "_modfl"
  - "modf"
  - "modfl"
  - "math/modf"
  - "math/modff"
  - "math/modfl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "modf (fonction)"
  - "modff (fonction)"
  - "modfl (fonction)"
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# modf, modff, modfl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Divise une valeur à virgule flottante en une fraction et un nombre entier.  
  
## Syntaxe  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### Paramètres  
 *x*  
 Valeur à virgule flottante.  
  
 `intptr`  
 Pointeur vers la partie entière stockée.  
  
## Valeur de retour  
 Cette fonction retourne la fraction signée de *x*. Aucun retour d'erreur.  
  
## Notes  
 Le `modf` fonctions diviser la valeur à virgule flottante `x` en une fraction et un nombre entier, chacun d’eux ayant la même signature que `x`. La fraction signée de `x` est retourné. La partie entière est stockée comme une valeur à virgule flottante `intptr.`  
  
 `modf` possède une implémentation qui utilise des Extensions Streaming SIMD 2 \(SSE2\). Consultez la page [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour plus d’informations et les restrictions sur l’utilisation de la mise en oeuvre SSE2.  
  
 C\+\+ autorise la surcharge, vous pouvez appeler des surcharges de `modf` qui acceptent et retournent `float` ou `long double` paramètres. Dans un programme C, `modf` toujours accepte deux valeurs doubles et retourne une valeur double.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`modf`, `modff`, `modfl`|C: \< math.h \><br /><br /> C\+\+ :, \< cmath \> ou \< math.h \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## Sortie  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)