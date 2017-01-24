---
title: "floor, floorf, floorl | Microsoft Docs"
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
  - "floorf"
  - "floorl"
  - "floor"
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
  - "floor"
  - "floorl"
  - "_floorl"
  - "floorf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "calculer des planchers de valeurs"
  - "floor (fonction)"
  - "floorf (fonction)"
  - "floorl (fonction)"
ms.assetid: e9955f70-d659-414f-8050-132e13c8ff36
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# floor, floorf, floorl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la partie entière d'une valeur.  
  
## Syntaxe  
  
```  
double floor(  
   double x  
);  
float floor(  
   float x   
); // C++ only  
long double floor(  
   long double x  
); // C++ only  
float floorf(  
   float x  
);  
long double floorl(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
## Valeur de retour  
 Les fonctions `floor` retournent une valeur à virgule flottante qui représente le plus grand entier inférieur ou égal à `x`.  Aucun retour d'erreur.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± QNAN,IND|aucun|\_DOMAIN|  
  
 `floor` a une implémentation qui utilise les extensions Streaming SIMD 2 \(SSE2\).  Pour plus d'informations et de restrictions sur l'utilisation de l'implémentation SSE2, consultez [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## Notes  
 C\+\+ permet la surcharge, donc il vous est possible d'appeler les surcharges de `floor` qui acceptent et retournent les valeurs `float` et `long double`.  Dans un programme C, `floor` prend et retourne toujours `double`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`floor`, `floorf`, `floorl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_floor.c  
// This example displays the largest integers  
// less than or equal to the floating-point values 2.8  
// and -2.8. It then shows the smallest integers greater  
// than or equal to 2.8 and -2.8.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double y;  
  
   y = floor( 2.8 );  
   printf( "The floor of 2.8 is %f\n", y );  
   y = floor( -2.8 );  
   printf( "The floor of -2.8 is %f\n", y );  
  
   y = ceil( 2.8 );  
   printf( "The ceil of 2.8 is %f\n", y );  
   y = ceil( -2.8 );  
   printf( "The ceil of -2.8 is %f\n", y );  
}  
```  
  
  **La partie entière de 2.8 est 2.000000**  
**La partie entière de \-2.8 est \-3.000000**  
**L'entier suivant la partie entière de 2,8 est 3,000000**  
**L'entier suivant la partie entière de \-2,8 est \-2,000000**   
## Équivalent .NET Framework  
 [System::Math::Floor](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)