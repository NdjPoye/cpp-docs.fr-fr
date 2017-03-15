---
title: "strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "strtoimax"
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
  - "wcstoimax"
  - "_tcstoimax"
  - "strtoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "_tcstoimax_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoimax_l (fonction)"
  - "_wcstoimax_l (fonction)"
  - "fonctions de conversion"
  - "strtoimax (fonction)"
  - "wcstoimax (fonction)"
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en valeur entière du plus grand type d'entier signé pris en charge.  
  
## Syntaxe  
  
```  
intmax_t strtoimax(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
intmax_t wcstoimax(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
intmax_t _strtoimax_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
intmax_t _wcstoimax_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `nptr`  
 Chaîne terminée par Null à convertir.  
  
 `endptr`  
 Pointeur vers le caractère qui arrête l'analyse.  
  
 `base`  
 Base numérique à utiliser.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `strtoimax` retourne la valeur qui est représentée dans la chaîne `nptr`, sauf lorsque la représentation provoque un dépassement de capacité, dans ce cas, elle retourne `INTMAX_MAX` ou `INTMAX_MIN`, et `errno` a la valeur `ERANGE`.  La fonction retourne 0 si aucune conversion ne peut être effectuée.  `wcstoimax` retourne les valeurs de façon analogue à `strtoimax`.  
  
 `INTMAX_MAX` et `INTMAX_MIN` sont définis dans stdint.h.  
  
 Si `nptr` est `NULL` ou `base` est différent de zéro et inférieurs à 2 ou supérieur à 36, `errno` a la valeur `EINVAL`.  
  
 Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `strtoimax` convertit `nptr` en `intmax_t`.  La version à caractères larges de `strtoimax` est `wcstoimax`; son argument `nptr` est une chaîne à caractères larges.  Sinon, ces fonctions se comportent sinon de façon identique.  Les deux fonctions cessent de lire la chaîne `nptr` au premier caractère qu'elles ne peuvent pas reconnaître comme faisant partie d'un nombre.  Il peut s'agir du caractère null de fin, ou il peut s'agir du premier caractère numérique supérieur ou égal à `base`.  
  
 Le paramètre de la catégorie `LC_NUMERIC` des paramètres régionaux détermine la reconnaissance des caractères de base dans `nptr`. Pour plus d'informations, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les fonctions qui ne disposent pas du suffixe `_l` utilisent les paramètres régionaux actuels ; `_strtoimax_l` et `_wcstoimax_l` sont identiques aux fonctions correspondantes qui ne disposent pas du suffixe `_l`, sauf qu'elles utilisent à la place les paramètres régionaux passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n'a pas la valeur `NULL`, un pointeur vers le caractère qui a arrêté l'analyse est enregistré à l'emplacement désigné par `endptr`.  Si aucune conversion ne peut être effectuée \(aucun chiffre valide n'a été trouvé ou une base non valide a été spécifiée\), la valeur de `nptr` est enregistrée à l'emplacement désigné par `endptr`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstoimax`|`strtoimax`|`strtoimax`|`wcstoimax`|  
|`_tcstoimax_l`|`strtoimax_l`|`_strtoimax_l`|`_wcstoimax_l`|  
  
 `strtoimax` attend `nptr` pour pointer vers une chaîne au format suivant :  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; `letters`\]  
  
 Un `whitespace` peut se composer d'espaces et de tabulations, qui sont ignorés ; `digits` se composent d'un ou plusieurs chiffres décimaux ; `letters` se composent d'une ou plusieurs lettres entre « a » et « z » \(ou de « A » à « Z »\).  Le premier caractère qui ne correspond pas à ce formulaire arrête l'analyse.  Si `base` est compris entre 2 et 36, il est utilisé comme base du nombre.  Si `base` est 0, les caractères initiaux de la chaîne désignée par `nptr` sont utilisés pour déterminer la base.  Si le premier caractère est « 0 » et le deuxième caractère n'est pas « x » ou « X », la chaîne est interprétée comme un entier octal.  Si le premier caractère est « 0 » et le deuxième caractère est « x » ou « X », la chaîne est interprétée comme un entier hexadécimal.  Si le premier caractère est compris entre « 1 » et « 9 », la chaîne est interprétée comme un entier décimal.  Les valeurs 10 à 35 sont assignées aux lettres « à » à « z » \(ou « À » à « Z »\) ; seules les lettres dont les valeurs assignées sont inférieures à `base` sont autorisées.  Le premier caractère en dehors de la plage de la base arrête l'analyse.  Par exemple, si `base` correspond à 0 et le premier caractère analysé est « 0 », un entier octal est supposé et un caractère « 8 » ou « 9 » arrêterait l'analyse.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strtoimax`, `_strtoimax_l`, `wcstoimax`, `_wcstoimax_l`|\<inttypes.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoumax, \_strtoumax\_l, wcstoumax, \_wcstoumax\_l](../../c-runtime-library/reference/strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)