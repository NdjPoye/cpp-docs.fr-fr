---
title: "pow, powf, powl | Microsoft Docs"
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
  - "powl"
  - "pow"
  - "powf"
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
  - "powl"
  - "pow"
  - "_powl"
  - "powf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_powl (fonction)"
  - "calculer les exponentiels"
  - "calculs exponentiels"
  - "élévation à la puissance"
  - "pow (fonction)"
  - "puissance, calculer"
  - "powf (fonction)"
  - "powl (fonction)"
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pow, powf, powl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule `x` élevé à la puissance de `y`.  
  
## Syntaxe  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### Paramètres  
 `x`  
 Base.  
  
 `y`  
 Exposant.  
  
## Valeur de retour  
 Retourne la valeur de `x`<sup>y</sup>.  Aucun message d'erreur n'est imprimé sur le dépassement de capacité inférieur ou supérieur.  
  
|Valeurs de X et Y|Valeur de retour de pow|  
|-----------------------|-----------------------------|  
|`x` \< \> 0 et `y` \= 0.0|1|  
|`x` \= 0.0 et `y` \= 0.0|1|  
|`x` \= 0.0 et `y` \< 0|INF|  
  
## Notes  
 `pow` ne reconnaît pas les valeurs à virgule flottante intégrales supérieures à 2<sup>64</sup> \(par exemple, `1.0E100`\).  
  
 `pow` a une implémentation qui utilise les extensions Streaming SIMD 2 \(SSE2\).  Pour plus d'informations et de restrictions sur l'utilisation de l'implémentation SSE2, consultez [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 Comme C\+\+ permet la surcharge, il vous est possible d'appeler différentes surcharges de`pow`.  Dans un programme C, `pow` prend toujours deux valeurs doubles et retourne une valeur double.  
  
 La surcharge de `pow(int, int)` n'est plus disponible.  Si vous utilisez cette surcharge, le compilateur peut émettre C2668.  Pour éviter ce problème, effectuez un cast du premier paramètre à `double`, `float`, ou `long double`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`pow`, `powf`, `powl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## Sortie  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## Équivalent .NET Framework  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [\_CIpow](../../c-runtime-library/cipow.md)