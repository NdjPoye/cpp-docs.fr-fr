---
title: strtol, wcstol, _strtol_l, _wcstol_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
dev_langs:
- C++
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e3555a209ba931c65080e833ba36f5de7d96a1ce
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol, wcstol, _strtol_l, _wcstol_l
Convertit les chaînes en valeur entière de type long.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
long strtol(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long wcstol(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long _strtol_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long _wcstol_l(  
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
 La fonction `strtol` retourne la valeur représentée dans la chaîne `nptr`, sauf dans le cas où la représentation entraînerait un dépassement de capacité positif, auquel cas elle retourne `LONG_MAX` ou `LONG_MIN`. `strtol` retourne 0 si aucune conversion ne peut être effectuée. `wcstol` retourne des valeurs de façon analogue à `strtol`. Pour les deux fonctions, `errno` prend la valeur `ERANGE` si un dépassement de capacité positif ou négatif se produit.  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `strtol` convertit `nptr` en `long`. La fonction `strtol` arrête de lire la chaîne `nptr` au premier caractère qu’elle ne peut pas identifier comme faisant partie intégrante d’un nombre. Il peut s’agir du caractère Null de fin ou bien du premier caractère numérique supérieur ou égal à `base`.  
  
 `wcstol` est une version à caractères larges de `strtol` ; son argument `nptr` est une chaîne de caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstol`|`strtol`|`strtol`|`wcstol`|  
|`_tcstol_l`|`_strtol_l`|`_strtol_l`|`_wcstol_l`|  
  
 La valeur du paramètre de catégorie `LC_NUMERIC` des paramètres régionaux actifs détermine la reconnaissance du caractère de base dans `nptr`*.* Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les fonctions sans suffixe `_l` utilisent les paramètres régionaux actifs ; `_strtol_l` et `_wcstol_l` sont identiques aux fonctions correspondantes sans suffixe `_l`, sauf qu’elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n’a pas la valeur `NULL`, un pointeur désignant le caractère qui a arrêté l’analyse est stocké à l’emplacement désigné par `endptr`. Si aucune conversion ne peut être effectuée (aucun chiffre valide n’a été trouvé ou la base spécifiée n’est pas valide), la valeur de `nptr` est stockée à l’emplacement désigné par `endptr`.  
  
 `strtol` s’attend à ce que `nptr` pointe vers une chaîne au format suivant :  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 Un `whitespace` peut être constitué d’espaces et de tabulations, qui sont ignorés ; `digits` se compose d’un ou plusieurs chiffres décimaux. Le premier caractère qui ne correspond pas à ce format a pour effet d’arrêter l’analyse. Si `base` a une valeur comprise entre 2 et 36, elle est utilisée comme base numérique. Si `base` a la valeur 0, les premiers caractères de la chaîne désignée par `nptr` servent à déterminer la base. Si le premier caractère est 0 et que le deuxième est différent de « x » ou « X », la chaîne est interprétée comme étant un entier octal. Si le premier caractère est « 0 » et que le deuxième est « x » ou « X », la chaîne est interprétée comme étant un entier hexadécimal. Si le premier caractère est un chiffre compris entre « 1 » et « 9 », la chaîne est interprétée comme étant un entier décimal. Les lettres de « a » à « z » (ou de « A » à « Z ») se voient affecter des valeurs comprises entre 10 et 35 ; seules sont autorisées les lettres dont les valeurs affectées sont inférieures à `base`. Le premier caractère situé en dehors de la plage de la base a pour effet d’arrêter l’analyse. Par exemple, si `base` est égal à 0 et que le premier caractère analysé est « 0 », il est supposé qu’il s’agit d’un entier octal et un caractère « 8 » ou « 9 » a pour effet de stopper l’analyse.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strtol`|\<stdlib.h>|  
|`wcstol`|\<stdlib.h> ou \<wchar.h>|  
|`_strtol_l`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)
