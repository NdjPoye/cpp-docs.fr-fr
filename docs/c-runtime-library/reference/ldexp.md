---
title: "ldexp | Microsoft Docs"
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
  - "ldexp"
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
  - "ldexp"
  - "_ldexpl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "calculer des nombres réels"
  - "calculer des nombres réels"
  - "exposant, chiffres à virgule flottante"
  - "fonctions en virgule flottante, mantisse et exposant"
  - "ldexp (fonction)"
  - "mantisses, variables à virgule flottante"
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ldexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Multiplie un nombre à virgule flottante par une puissance intégrale de deux.  
  
## Syntaxe  
  
```  
double ldexp(    double x,    int exp  ); float ldexp(    float x,    int exp );  // C++ only long double ldexp(    long double x,    int exp );  // C++ only  float ldexpf(    float x,    int exp );  long double ldexpl(    long double x,    int exp );   
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
 `exp`  
 Exposant entier.  
  
## Valeur de retour  
 La fonction `ldexp` retourne la valeur `x` \* 2<sup>exp</sup> en cas de succès.  En cas de dépassement et selon le signe de `x`, `ldexp` retourne \+\/– `HUGE_VAL` ; `errno` a la valeur `ERANGE`.  
  
 Pour plus d'informations sur `errno` et sur les valeurs de retour d'erreur possibles, voir [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `ldexp` qui acceptent des types `float` ou `long double`.  Dans un programme C, `ldexp` accepte toujours `double` et `int`, et retourne `double`.  
  
## Configuration requise  
  
|Routine|En\-tête C|En\-tête C\+\+|  
|-------------|----------------|--------------------|  
|`ldexp`, `ldexpf`, `ldexpl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_ldexp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 4.0, y;  
   int p = 3;  
  
   y = ldexp( x, p );  
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## Sortie  
  
```  
4.0 times two to the power of 3 is 32.0  
```  
  
## Équivalent .NET Framework  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)