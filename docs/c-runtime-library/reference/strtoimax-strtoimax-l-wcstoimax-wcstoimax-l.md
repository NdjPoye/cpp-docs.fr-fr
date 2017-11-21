---
title: strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstoimax
- _tcstoimax
- strtoimax
- _wcstoimax_l
- _strtoimax_l
- _tcstoimax_l
dev_langs: C++
helpviewer_keywords:
- strtoimax funciton
- conversion functions
- _strtoimax_l function
- _wcstoimax_l function
- wcstoimax function
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b1e6ebcd650aba561e82ed1597429144ba175185
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="strtoimax-strtoimaxl-wcstoimax-wcstoimaxl"></a>strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
Convertit une chaîne en valeur entière du type d’entier signé pris en charge le plus grand.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `nptr`  
 Chaîne se terminant par un caractère Null à convertir.  
  
 `endptr`  
 Pointeur désignant le caractère qui arrête l’analyse.  
  
 `base`  
 Base numérique à utiliser.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 La fonction `strtoimax` retourne la valeur représentée dans la chaîne `nptr`, sauf dans le cas où la représentation entraînerait un dépassement de capacité positif (dans ce cas, elle retourne `INTMAX_MAX` ou `INTMAX_MIN` et `errno` prend la valeur `ERANGE`). La fonction retourne 0 si aucune conversion ne peut être effectuée. `wcstoimax` retourne des valeurs de façon analogue à `strtoimax`.  
  
 `INTMAX_MAX` et `INTMAX_MIN` sont définis dans stdint.h.  
  
 Si `nptr` a la valeur `NULL` ou que `base` est différent de zéro et inférieur à 2 ou supérieur à 36, `errno` prend la valeur `EINVAL`.  
  
 Pour plus d’informations sur les codes de retour, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `strtoimax` convertit `nptr` en `intmax_t`. La version à caractères larges de `strtoimax` est `wcstoimax` ; son argument `nptr` est une chaîne de caractères larges. Sinon, ces fonctions se comportent de façon identique. Les deux fonctions arrêtent de lire la chaîne `nptr` au premier caractère qu’elles ne peuvent pas identifier comme faisant partie intégrante d’un nombre. Il peut s’agir du caractère null de fin ou bien du premier caractère numérique supérieur ou égal à `base`.  
  
 La valeur du paramètre de catégorie `LC_NUMERIC` des paramètres régionaux détermine la reconnaissance du caractère de base dans `nptr`. Pour plus d’informations, consultez [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les fonctions sans suffixe `_l` utilisent les paramètres régionaux actifs ; `_strtoimax_l` et `_wcstoimax_l` sont identiques aux fonctions correspondantes qui n’ont pas le suffixe `_l`, sauf qu’elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n’a pas la valeur `NULL`, un pointeur désignant le caractère qui a arrêté l’analyse est stocké à l’emplacement désigné par `endptr`. Si aucune conversion ne peut être effectuée (aucun chiffre valide n’a été trouvé ou la base spécifiée n’est pas valide), la valeur de `nptr` est stockée à l’emplacement désigné par `endptr`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoimax`|`strtoimax`|`strtoimax`|`wcstoimax`|  
|`_tcstoimax_l`|`strtoimax_l`|`_strtoimax_l`|`_wcstoimax_l`|  
  
 `strtoimax` s’attend à ce que `nptr` pointe vers une chaîne au format suivant :  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; `letters`]  
  
 `whitespace` peut être constitué d’espaces et de tabulations, qui sont ignorés ; `digits` se compose d’un ou plusieurs chiffres décimaux ; `letters` comprend une ou plusieurs lettres, de « a » à « z » (ou de « A » à « Z »). Le premier caractère qui ne correspond pas à ce format a pour effet d’arrêter l’analyse. Si `base` a une valeur comprise entre 2 et 36, elle est utilisée comme base numérique. Si `base` a la valeur 0, les premiers caractères de la chaîne désignée par `nptr` servent à déterminer la base. Si le premier caractère est « 0 » et que le deuxième est différent de « x » ou « X », la chaîne est interprétée comme étant un entier octal. Si le premier caractère est « 0 » et que le deuxième est « x » ou « X », la chaîne est interprétée comme étant un entier hexadécimal. Si le premier caractère est un chiffre compris entre « 1 » et « 9 », la chaîne est interprétée comme étant un entier décimal. Les lettres de « a » à « z » (ou de « A » à « Z ») se voient affecter des valeurs comprises entre 10 et 35 ; seules sont autorisées les lettres dont les valeurs affectées sont inférieures à `base`. Le premier caractère situé en dehors de la plage de la base a pour effet d’arrêter l’analyse. Par exemple, si `base` est égal à 0 et que le premier caractère analysé est « 0 », il est considéré comme étant un entier octal et un caractère « 8 » ou « 9 » a pour effet d’arrêter l’analyse.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strtoimax`, `_strtoimax_l`, `wcstoimax`, `_wcstoimax_l`|\<inttypes.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l](../../c-runtime-library/reference/strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)