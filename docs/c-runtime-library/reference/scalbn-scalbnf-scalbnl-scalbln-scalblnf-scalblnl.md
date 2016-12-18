---
title: "scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft Docs"
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
  - "scalblnl"
  - "scalbnl"
  - "scalbnf"
  - "scalblnf"
  - "scalbn"
  - "scalbln"
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
  - "scalblnf"
  - "scalbnl"
  - "scalblnl"
  - "scalbln"
  - "scalbn"
  - "scalbnf"
dev_langs: 
  - "C++"
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Multiplie un nombre à virgule flottante par une puissance intégrale de FLT\_RADIX.  
  
## Syntaxe  
  
```  
double scalbn(    double x,    int exp  ); float scalbn(    float x,    int exp );  // C++ only long double scalbn(    long double x,    int exp );  // C++ only  float scalbnf(    float x,    int exp );  long double scalbnl(    long double x,    int exp ); double scalbln(    double x,    long exp  ); float scalbln(    float x,    long exp );  // C++ only long double scalbln(    long double x,    long exp );  // C++ only  float scalblnf(    float x,    long exp );  long double scalblnl(    long double x,    long exp );  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
 `exp`  
 Exposant entier.  
  
## Valeur de retour  
 Les fonctions `scalbn` retournent la valeur `x` \* `FLT_RADIX`<sup>exp</sup> en cas de succès.  En cas de dépassement \(selon le signe de `x`\), `scalbn` retourne \+\/– `HUGE_VAL` ; `errno` a la valeur `ERANGE`.  
  
 Pour plus d'informations sur `errno` et sur les valeurs de retour d'erreur possibles, voir [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 `FLT_RADIX` est défini dans \<float.h\> comme base à virgule flottante native ; sur les systèmes binaires, sa valeur est égale à 2 et `scalbn` est équivalent à [ldexp](../../c-runtime-library/reference/ldexp.md).  
  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `scalbn` et `scalbln` qui acceptent et retournent des types `float` ou `long double`.  Dans un programme C, `scalbn` accepte toujours une valeur `double` et une valeur `int`, et retourne une valeur `double`, et `scalbln` accepte toujours une valeur `double` et une valeur `long`, et retourne une valeur `double`.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## Sortie  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## Équivalent .NET Framework  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)