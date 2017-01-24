---
title: "fmod, fmodf | Microsoft Docs"
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
  - "fmod"
  - "fmodf"
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
  - "fmod"
  - "_fmodl"
  - "fmodf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "calculer les restes de quantités à virgule flottante"
  - "fmodf (fonction)"
  - "fmod (fonction)"
  - "nombres à virgule flottante, calculer les restes"
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fmod, fmodf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le reste en virgule flottante.  
  
## Syntaxe  
  
```  
double fmod(   
   double x,  
   double y   
);  
float fmod(  
   float x,  
   float y   
);  // C++ only  
long double fmod(  
   long double x,  
   long double y  
);  // C++ only  
float fmodf(   
   float x,  
   float y   
);  
```  
  
#### Paramètres  
 `x`, `y`  
 Valeurs à virgule flottante  
  
## Valeur de retour  
 `fmod` retourne le reste à virgule flottante de `x` \/ `y`.  Si `y` a la valeur 0.0, `fmod` retourne un quiet NaN.  Pour plus d'informations sur la représentation d'un quiet NaN par la famille `printf`, consultez [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## Notes  
 La fonction `fmod` calcule le reste à virgule flottante `f` de `x` \/ `y` comme `x` \= `i` `*` `y` \+ `f`, où `i` est un entier, `f` a le même signe que `x`, et la valeur absolue `f` est inférieure à la valeur absolue `y`.  
  
 Comme le C\+\+ permet la surcharge de méthode, vous pouvez appeler des surcharges de `fmod`.  Dans un programme C, `fmod` prend deux doubles et retourne toujours un double.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fmod`, `fmodf`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fmod.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = fmod( w, x );  
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );  
}  
```  
  
  **Le reste de \-10,00\/3,00 est \-1,000000**   
## Équivalent .NET Framework  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [\_CIfmod](../../c-runtime-library/cifmod.md)