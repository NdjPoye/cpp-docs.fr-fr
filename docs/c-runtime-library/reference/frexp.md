---
title: "frexp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "frexp"
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
  - "frexp"
  - "_frexpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_frexpl (fonction)"
  - "exposant, chiffres à virgule flottante"
  - "fonctions en virgule flottante, mantisse et exposant"
  - "frexp (fonction)"
  - "frexpl (fonction)"
  - "mantisses, variables à virgule flottante"
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# frexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la mantisse et l'exposant d'un nombre à virgule flottante.  
  
## Syntaxe  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
 `expptr`  
 Pointeur vers l'exposant entier stocké.  
  
## Valeur de retour  
 `frexp` retourne la mantisse.  Si `x` est 0, la fonction retourne 0 pour la mantisse et l'exposant.  Si `expptr` est `NULL`, le gestionnaire de paramètres invalide est appelé comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` à la valeur `EINVAL` et retourne 0.  
  
## Notes  
 La fonction `frexp` décompose la valeur à virgule flottante \(`x`\) en une mantisse \(`m`\) et un exposant \(`n`\), de sorte que la valeur absolue de `m` est supérieure ou égale à 0,5 et inférieure à 1,0, et que `x` \= `m`. \*2.<sup>n</sup> L'exposant entier `n` est enregistré à l'emplacement désigné par `expptr`.  
  
 Comme le C\+\+ permet la surcharge de méthode, vous pouvez appeler des surcharges de `frexp`.  Dans un programme C, `frexp` prend toujours un double et un entier et retourne une valeur double.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`frexp`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
  **frexp \(16,400000\), &n \= 0,512500, n \= 5**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)