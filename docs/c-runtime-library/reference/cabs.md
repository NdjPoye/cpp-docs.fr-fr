---
title: "_cabs | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cabs"
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
  - "cabsl"
  - "_cabs"
  - "_cabsl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cabs (fonction)"
  - "_cabsl (fonction)"
  - "valeurs absolues"
  - "cabs (fonction)"
  - "cabsl (fonction)"
  - "calculer des valeurs absolues"
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cabs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la valeur absolue d'un nombre complexe.  
  
## Syntaxe  
  
```  
double _cabs(   
   struct _complex z   
);  
```  
  
#### Paramètres  
 `z`  
 Nombre complexe.  
  
## Valeur de retour  
 `_cabs` retourne la valeur absolue de l'argument en cas de réussite.  Sur le dépassement de capacité, `_cabs` retourne `HUGE_VAL` et définit `errno` à `ERANGE`.  Vous pouvez modifier la gestion des erreurs avec [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Notes  
 La fonction `_cabs` calcule la valeur absolue d'un nombre complexe, qui doit être une structure du type [\_complex](../../c-runtime-library/standard-types.md).  La structure `z` est composée d'une partie réelle `x` et d'une partie imaginaire `y`.  Un appel à `_cabs` produit une valeur équivalente à celle de l'expression `sqrt`\( `z.x``*``z.x` `+` `z.y`\*`z.y` \).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_cabs`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_cabs.c  
/* Using _cabs, this program calculates  
 * the absolute value of a complex number.  
 */  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct _complex number = { 3.0, 4.0 };  
   double d;  
  
   d = _cabs( number );  
   printf( "The absolute value of %f + %fi is %f\n",  
           number.x, number.y, d );  
}  
```  
  
  **La valeur absolue de 3,000000 \+ 4,000000i est 5.000000**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ABS, laboratoires, llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [labs, llabs](../../misc/labs-llabs.md)