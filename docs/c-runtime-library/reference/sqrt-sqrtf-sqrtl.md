---
title: "sqrt, sqrtf, sqrtl | Microsoft Docs"
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
  - "sqrtl"
  - "sqrtf"
  - "sqrt"
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
  - "sqrt"
  - "sqrtf"
  - "_sqrtl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_sqrtl (fonction)"
  - "calculer les racines carrées"
  - "sqrt (fonction)"
  - "sqrtf (fonction)"
  - "sqrtl (fonction)"
  - "racines carrées, calculer"
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sqrt, sqrtf, sqrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la racine carrée.  
  
## Syntaxe  
  
```  
double sqrt(    double x  ); float sqrt(    float x  );  // C++ only long double sqrt(    long double x );  // C++ only float sqrtf(    float x  ); long double sqrtl(    long double x  );  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante non négative  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `sqrt` qui acceptent les types `float` ou `long double`.  Dans un programme C, `sqrt` accepte et retourne toujours `double`.  
  
## Valeur de retour  
 Les fonctions `sqrt` retournent la racine carrée de `x`.  Par défaut, si `x` est négatif, `sqrt` retourne une valeur NaN indéfinie.  
  
|Entrée|Exception SEH|Exception `_matherr`|  
|------------|-------------------|--------------------------|  
|± QNAN,IND|aucun|\_DOMAIN|  
|\- ∞|aucun|\_DOMAIN|  
|x\<0|aucun|\_DOMAIN|  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`sqrt`, `sqrtf`, `sqrtl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_sqrt.c  
// This program calculates a square root.  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   double question = 45.35, answer;  
   answer = sqrt( question );  
   if( question < 0 )  
      printf( "Error: sqrt returns %f\n", answer );  
   else  
      printf( "The square root of %.2f is %.2f\n", question, answer );  
}  
```  
  
  **The square root of 45.35 is 6.73**   
## Équivalent .NET Framework  
 [System::Math::Sqrt](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [\_CIsqrt](../../c-runtime-library/cisqrt.md)