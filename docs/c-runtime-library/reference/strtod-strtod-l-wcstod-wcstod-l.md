---
title: "strtod, _strtod_l, wcstod, _wcstod_l | Microsoft Docs"
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
  - "wcstod"
  - "_wcstod_l"
  - "_strtod_l"
  - "strtod"
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
  - "_tcstod"
  - "strtod"
  - "wcstod"
  - "_strtod_l"
  - "_wcstod_l"
  - "stdlib/strtod"
  - "corecrt_wstdlib/wcstod"
  - "stdlib/_strtod_l"
  - "corecrt_wstdlib/_wcstod_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtod_l (fonction)"
  - "_tcstod (fonction)"
  - "_tcstod_l (fonction)"
  - "_wcstod_l (fonction)"
  - "conversion de chaînes, en valeurs à virgule flottante"
  - "strtod (fonction)"
  - "strtod_l (fonction)"
  - "tcstod (fonction)"
  - "tcstod_l (fonction)"
  - "wcstod (fonction)"
  - "wcstod_l (fonction)"
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
caps.latest.revision: 20
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtod, _strtod_l, wcstod, _wcstod_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaînes en une valeur de "double\-precision".  
  
## Syntaxe  
  
```  
double strtod(  
   const char *nptr,  
   char **endptr   
);  
double _strtod_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
double wcstod(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
double wcstod_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `nptr`  
 Chaîne terminée par Null à convertir.  
  
 `endptr`  
 Pointeur vers le caractère qui arrête l'analyse.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `strtod` retourne la valeur du nombre à virgule flottante, sauf lorsque la représentation provoque un dépassement de capacité, auquel cas la fonction retourne la valeur \+\/\-`HUGE_VAL`.  Le signe de `HUGE_VAL` correspond au signe de la valeur qui ne peut pas être représentée.  `strtod` retourne 0 si aucune conversion ne peut être exécutée ou un dépassement de capacité se produit.  
  
 `wcstod` retourne les valeurs de façon analogue à `strtod`.  Pour les deux fonctions, `errno` a la valeur `ERANGE` en cas de surcapacité ou de sous\-capacité et en cas d'appel du gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ceci et d'autres codes de retour.  
  
## Notes  
 Chaque fonction convertit la chaîne d'entrée `nptr` en `double`.  La fonction `strtod` convertit `nptr` en une valeur double\-précision.  La fonction `strtod` arrête de lire la chaîne `nptr` au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Il peut s'agir du caractère null de fin.  `wcstod` est une version à caractères larges de `strtod`; son argument `nptr` est une chaîne à caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstod`|`strtod`|`strtod`|`wcstod`|  
|`_tcstod_l`|`_strtod_l`|`_strtod_l`|`_wcstod_l`|  
  
 Le paramètre de catégorie `LC_NUMERIC` des paramètres régionaux actuels détermine la reconnaissance des caractères de base dans `nptr`*;* pour plus d'informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les fonctions sans le suffixe `_l` utilisent les paramètres régionaux locaux ; `_strtod_l` est identique à `_strtod_l` sauf qu'elles utilisent à la place les paramètres régionaux qui lui sont transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n'a pas la valeur `NULL`, un pointeur vers le caractère qui a arrêté l'analyse est enregistré à l'emplacement désigné par `endptr`.  Si aucune conversion ne peut être effectuée \(aucun chiffre valide n'a été trouvé ou une base non valide a été spécifiée\), la valeur de `nptr` est enregistrée à l'emplacement désigné par `endptr`.  
  
 `strtod` attend `nptr` pour pointer vers une chaîne au format suivant :  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 Un `whitespace` peut se composer d'espaces et de caractères de tabulations, qui sont ignorés ; un `sign` est soit plus \(`+`\) soit moins \(`–`\) ; et des `digits` se composent d'un ou plusieurs chiffres décimaux.  Si aucun chiffre ne s'affiche avant le caractère de base, au moins un doit apparaître après le caractère de base.  Les nombres décimaux peuvent être suivis d'un exposant, qui comprend une lettre préliminaire \(`d`, `D`, `e` ou `E`\) et éventuellement un entier signé.  Si ni une partie d'exposant ni un caractère de base n'apparaît, il suppose qu'un caractère de base suit le dernier chiffre dans la chaîne.  Le premier caractère qui ne correspond pas à ce formulaire arrête l'analyse.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strtod`, `_strtod_l`|\<stdlib.h\>|  
|`wcstod`, `_wcstod_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_strtod.c  
// This program uses strtod to convert a  
// string to a double-precision value; strtol to  
// convert a string to long integer values; and strtoul  
// to convert a string to unsigned long-integer values.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char   *string, *stopstring;  
   double x;  
   long   l;  
   int    base;  
   unsigned long ul;  
  
   string = "3.1415926This stopped it";  
   x = strtod( string, &stopstring );  
   printf( "string = %s\n", string );  
   printf("   strtod = %f\n", x );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "-10110134932This stopped it";  
   l = strtol( string, &stopstring, 10 );  
   printf( "string = %s\n", string );  
   printf("   strtol = %ld\n", l );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "10110134932";  
   printf( "string = %s\n", string );  
  
   // Convert string using base 2, 4, and 8:  
   for( base = 2; base <= 8; base *= 2 )  
   {  
      // Convert the string:  
      ul = strtoul( string, &stopstring, base );  
      printf( "   strtol = %ld (base %d)\n", ul, base );  
      printf( "   Stopped scan at: %s\n", stopstring );  
   }  
}  
```  
  
  **string \= 3.1415926This l'a arrêté**  
 **strtod \= 3.141593**  
 **Analyse arrêtée à : Cela l'a arrêté**  
**string \= \-10110134932This l'a arrêté**  
 **strtol \= \-2147483648**  
 **Analyse arrêtée à : Cela l'a arrêté**  
**chaîne \= 10110134932**  
 **strtol \= 45 \(base 2\)**  
 **Analyse arrêtée à : 34932**  
 **strtol \= 4423 \(base 4\)**  
 **Analyse arrêtée à : 4932**  
 **strtol \= 2134108 \(base 8\)**  
 **Analyse arrêtée à : 932**   
## Équivalent .NET Framework  
 [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)