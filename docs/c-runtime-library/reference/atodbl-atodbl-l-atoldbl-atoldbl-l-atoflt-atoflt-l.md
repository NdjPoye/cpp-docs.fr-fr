---
title: "_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_atoldbl"
  - "_atoldbl_l"
  - "_atodbl"
  - "_atoflt"
  - "_atoflt_l"
  - "_atodbl_l"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_atoflt"
  - "_atoflt_l"
  - "atodbl_l"
  - "atoflt_l"
  - "_atoldbl"
  - "_atoldbl_l"
  - "atodbl"
  - "_atodbl_l"
  - "atoldbl"
  - "atoflt"
  - "atoldbl_l"
  - "_atodbl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_atodbl (fonction)"
  - "_atoldbl_l (fonction)"
  - "atoflt (fonction)"
  - "atoflt_l (fonction)"
  - "atoldbl (fonction)"
  - "_atoldbl (fonction)"
  - "atodbl_l (fonction)"
  - "_atoflt_l (fonction)"
  - "atoldbl_l (fonction)"
  - "atodbl (fonction)"
  - "conversion de chaînes, en valeurs à virgule flottante"
  - "_atoflt (fonction)"
  - "_atodbl_l (fonction)"
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne de caractères en un double \(`_atodbl`\), un long double \(`_atoldbl`\), ou un float \(`_atoflt`\).  
  
## Syntaxe  
  
```  
int _atodbl(  
   _CRT_DOUBLE * value,  
   char * str  
);  
int _atodbl_l (  
   _CRT_DOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoldbl(  
   _LDOUBLE * value,  
   char * str  
);  
int _atoldbl_l (  
   _LDOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoflt(  
   _CRT_FLOAT * value,  
   const char * str  
);  
int _atoflt_l(  
   _CRT_FLOAT * value,  
   const char * str,  
   locale_t locale  
);  
```  
  
#### Paramètres  
 `value`  
 La valeur du double, du long double, ou du float qui est produite lors de la conversion de la chaîne en une valeur à virgule flottante.  Ces valeurs sont encapsulées dans une structure.  
  
 `str`  
 La chaîne de caractère à analyser pour convertir en une valeur à virgule flottante.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 En cas de réussite, retourne 0.  Les codes d'erreur possibles sont `_UNDERFLOW` ou `_OVERFLOW`, qui sont définis dans le fichier d'en\-tête Math.h.  
  
## Notes  
 Ces fonctions convertissent une chaîne en une valeur à virgule flottante.  La différence entre ces fonctions et la famille de fonctions `atof` est que ces fonctions ne génèrent pas de code à virgule flottante et n'entraînent pas d'exceptions matérielles.  À la place, les conditions d'erreur sont signalées comme des codes d'erreur.  
  
 Si une chaîne n'a pas d'interprétation valide comme valeur à virgule flottante, `value` est mis à zéro et la valeur de retour est zéro.  
  
 Les versions des fonctions qui disposent du suffixe `_l` sont identiques aux versions qui n'en disposent pas, sauf qu'elles utilisent les paramètres régionaux passés au lieu du thread de paramètres régionaux actuel.  
  
## Configuration requise  
  
|Routines|En\-tête requis|  
|--------------|---------------------|  
|`_atodbl`, `_atoldbl`, `_atoflt`<br /><br /> `_atodbl_l`, `_atoldbl_l`, `_atoflt_l`|\<stdlib.h\>|  
  
## Exemple  
  
```  
// crt_atodbl.c  
// Uses _atodbl to convert a string to a double precision  
// floating point value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
   char str1[256] = "3.141592654";  
   char abc[256] = "abc";  
   char oflow[256] = "1.0E+5000";  
   _CRT_DOUBLE dblval;  
   _CRT_FLOAT fltval;  
   int retval;  
  
   retval = _atodbl(&dblval, str1);  
  
   printf("Double value: %lf\n", dblval.x);  
   printf("Return value: %d\n\n", retval);  
  
   retval = _atoflt(&fltval, str1);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // A non-floating point value: returns 0.  
   retval = _atoflt(&fltval, abc);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // Overflow.  
   retval = _atoflt(&fltval, oflow);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   return 0;  
}  
```  
  
  **Valeur double : 3.141593**  
**Valeur de retour : 0**  
**Valeur du float : 3,141593**  
**Valeur de retour : 0**  
**Valeur du float : 0,000000**  
**Valeur de retour : 0**  
**Valeur du float : 1.\#INF00**  
**Valeur de retour : 3**   
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)