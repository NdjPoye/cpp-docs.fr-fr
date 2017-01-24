---
title: "strtof, _strtof_l, wcstof, _wcstof_l | Microsoft Docs"
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
  - "_strtof_l"
  - "wcstof"
  - "strtof"
  - "_wcstof_l"
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
  - "_tcstof"
  - "_tcstof_l"
  - "stdlib/strtof"
  - "strtof"
  - "stdlib/_strtof_l"
  - "_strtof_l"
  - "corecrt_wstdlib/wcstof"
  - "wcstof"
  - "corecrt_wstdlib/_wcstof_l"
  - "_wcstof_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtof_l (fonction)"
  - "_tcstof (fonction)"
  - "_tcstof_l (fonction)"
  - "_wcstof_l (fonction)"
  - "strtof (fonction)"
  - "wcstof (fonction)"
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
caps.latest.revision: 9
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtof, _strtof_l, wcstof, _wcstof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit les chaînes en une valeur à virgule flottante simple précision.  
  
## Syntaxe  
  
```  
float strtof(  
   const char *nptr,  
   char **endptr   
);  
float _strtof_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
float wcstof(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
float wcstof_l(  
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
 `strtof` retourne la valeur du nombre à virgule flottante, sauf lorsque la représentation provoque un dépassement de capacité, auquel cas la fonction retourne la valeur \+\/\-`HUGE_VALF`.  Le signe de `HUGE_VALF` correspond au signe de la valeur qui ne peut pas être représentée.  `strtof` retourne 0 si aucune conversion ne peut être exécutée ou un dépassement de capacité se produit.  
  
 `wcstof` retourne les valeurs de façon analogue à `strtof`.  Pour les deux fonctions, `errno` a la valeur `ERANGE` en cas de surcapacité ou de sous\-capacité et en cas d'appel du gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chaque fonction convertit la chaîne d'entrée `nptr` en `float`.  La fonction `strtof` convertit `nptr` en une valeur simple précision.  La fonction `strtof` arrête de lire la chaîne `nptr` au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Il peut s'agir du caractère null de fin.  `wcstof` est une version à caractères larges de `strtof`; son argument `nptr` est une chaîne à caractères larges.  Sinon, ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstof`|`strtof`|`strtof`|`wcstof`|  
|`_tcstof_l`|`_strtof_l`|`_strtof_l`|`_wcstof_l`|  
  
 Le paramètre de la catégorie `LC_NUMERIC` des paramètres régionaux actuels détermine la reconnaissance des caractères de base dans `nptr`. Pour plus d'informations, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les fonctions qui ne disposent pas du suffixe `_l` utilisent les paramètres régionaux actuels ; celles qui disposent du suffixe sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n'a pas la valeur `NULL`, un pointeur vers le caractère qui a arrêté l'analyse est enregistré à l'emplacement désigné par `endptr`.  Si aucune conversion ne peut être effectuée \(aucun chiffre valide n'a été trouvé ou une base non valide a été spécifiée\), la valeur de `nptr` est enregistrée à l'emplacement désigné par `endptr`.  
  
 `strtof` attend `nptr` pour pointer vers une chaîne au format suivant :  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 Un `whitespace` peut se composer d'espaces et de caractères de tabulations, qui sont ignorés ; un `sign` est soit plus \(`+`\) soit moins \(`–`\) ; et des `digits` se composent d'un ou plusieurs chiffres décimaux.  Si aucun chiffre ne s'affiche avant le caractère de base, au moins un doit apparaître après le caractère de base.  Les nombres décimaux peuvent être suivis d'un exposant, qui comprend une lettre préliminaire \(`d`, `D`, `e` ou `E`\) et éventuellement un entier signé.  Si ni une partie d'exposant ni un caractère de base n'apparaît, il suppose qu'un caractère de base suit le dernier chiffre dans la chaîne.  Le premier caractère qui ne correspond pas à ce formulaire arrête l'analyse.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strtof`, `_strtof_l`|\<stdlib.h\>|  
|`wcstof`, `_wcstof_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strtof.c  
// This program uses strtof to convert a  
// string to a single-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   float x;  
  
   string = "3.14159This stopped it";  
   x = strtof(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtof = %f\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
  **string \= 3.14159This stopped it**  
 **strtof \= 3.141590**  
 **Analyse arrêtée à : Cela l'a arrêté**   
## Équivalent .NET Framework  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)