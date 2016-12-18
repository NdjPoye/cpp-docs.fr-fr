---
title: "remquo, remquof, remquol | Microsoft Docs"
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
  - "remquof"
  - "remquo"
  - "remquol"
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
  - "remquof"
  - "remquol"
  - "remquo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remquol (fonction)"
  - "remquof (fonction)"
  - "remquo (fonction)"
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remquo, remquof, remquol
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le reste de deux valeurs entières, et stocke une valeur entière avec le signe et l'ampleur approximative du quotient dans un emplacement spécifié dans un paramètre.  
  
## Syntaxe  
  
```  
double remquo(   
   double numer,  
   double denom,  
   int* quo  
);  
float remquo(   
   float numer,  
   float denom,  
   int* quo  
); /* C++ only */  
long double remquo(   
   long double numer,  
   long double denom,  
   int* quo  
); /* C++ only */  
float remquof(   
   float numer,  
   float denom,  
   int* quo  
);  
long double remquol(   
   long double numer,  
   long double denom,  
   int* quo  
);  
  
```  
  
#### Paramètres  
 `numer`  
 Le numérateur.  
  
 `denom`  
 Le dénominateur.  
  
 `quo`  
 Pointeur vers un entier pour stocker une valeur qui possède le signe et l'ampleur approximative du quotient.  
  
## Valeur de retour  
 `remquo` retourne le reste à virgule flottante de `x` \/ `y`.  Si `y` a la valeur 0.0, `remquo` retourne un quiet NaN.  Pour plus d'informations sur la représentation d'un quiet NaN par la famille `printf`, consultez [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## Notes  
 La fonction `remquo` calcule le reste à virgule flottante `f` de `x` \/ `y` comme `x` \= `i` `*` `y` \+ `f`, où `i` est un entier, `f` a le même signe que `x`, et la valeur absolue `f` est inférieure à la valeur absolue `y`.  
  
 C\+\+ permet la surcharge, donc vous pouvez appeler les surcharges de `remquo` qui acceptent et retournent les valeurs `float` ou `long double`.  Dans un programme C, `remquo` prend deux doubles et retourne toujours un double.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`remquo`, `remquof`, `remquol`|\<math.h\>|  
  
 Pour des informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```c  
// crt_remquo.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
   int quo = 0;  
  
   z = remquo(w, x, &quo);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
   printf("Approximate signed quotient is %d\n", quo);  
}  
```  
  
  **Le reste de \-10,00\/3,00 est \-1,000000**  
**Le quotient signé approximatif est \-3**   
## Équivalent .NET Framework  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)