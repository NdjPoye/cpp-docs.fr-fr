---
title: "exp, expf | Microsoft Docs"
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
  - "expf"
  - "exp"
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
  - "_expl"
  - "expf"
  - "exp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "calculs exponentiels"
  - "expf (fonction)"
  - "calculer les exponentiels"
  - "exp (fonction)"
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exp, expf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule l'exponentielle.  
  
## Syntaxe  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
## Valeur de retour  
 La fonction `exp` renvoie la valeur exponentielle du paramètre à virgule flottante, `x`, en cas de succès.  Autrement dit, le résultat est e à la puissance `x`, où e est la base du logarithme népérien.  En cas de dépassement de capacité par valeur supérieure, la fonction retourne INF \(infini\) et En cas de dépassement de capacité par valeur inférieure, `exp` retourne 0.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± QNAN,IND|None|\_DOMAIN|  
|± ∞|NON VALIDE|\_DOMAIN|  
|X ≥ 7.097827e\+002|INEXACT\+OVERFLOW|Dépassement de capacité.|  
|X ≤ \-7.083964e\+002|INEXACT\+UNDERFLOW|UNDERFLOW|  
  
 `exp` a une implémentation qui utilise les extensions Streaming SIMD 2 \(SSE2\).  Voir le [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour des informations ainsi que connaitre l'état des restrictions sur l'usage de l'implémentation SSE2.  
  
## Notes  
 Comme le C\+\+ permet la surcharge de méthode, vous pouvez appeler des surcharges de `exp`.  Dans un programme C, `exp` prend en argument et retourne toujours un double.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`exp`, `expf`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
  **exp\( 2.302585 \) \= 10.000000**   
## Équivalent .NET Framework  
 [System::Math::Exp](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [\_CIexp](../../c-runtime-library/ciexp.md)