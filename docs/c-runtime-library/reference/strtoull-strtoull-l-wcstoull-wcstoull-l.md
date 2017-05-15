---
title: strtoull, _strtoull_l, wcstoull, _wcstoull_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strtoull_l
- _wcstoull_l
- strtoull
- wcstoull
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
- _wcstoull_l
- _tcstoull
- _tcstoull_l
- wcstoull
- _strtoull_l
- strtoull
dev_langs:
- C++
helpviewer_keywords:
- strtoull function
- _tcstoull_l function
- _tcstoull function
- _wcstoull_l function
- _strtoull_l function
- wcstoull function
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
caps.latest.revision: 5
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
ms.openlocfilehash: 7ab47ad852aa8b389b20767f5aa3b969368af012
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="strtoull-strtoulll-wcstoull-wcstoulll"></a>strtoull, _strtoull_l, wcstoull, _wcstoull_l
Convertit les chaînes en valeur entière de type long long non signée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned long long strtoull(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long long _strtoull_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long long wcstoull(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long long _wcstoull_l(  
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
 `strtoull` retourne la valeur convertie, le cas échéant, ou `ULLONG_MAX` en cas de dépassement de capacité positif. `strtoull` retourne 0 si aucune conversion ne peut être effectuée. `wcstoull` retourne des valeurs de façon analogue à `strtoull`. Pour les deux fonctions, `errno` prend la valeur `ERANGE` si un dépassement de capacité positif ou négatif se produit.  
  
 Pour plus d’informations sur les codes de retour, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions convertit la chaîne d’entrée `nptr` en valeur entière `unsigned long long`.  
  
 La fonction `strtoull` arrête de lire la chaîne `nptr` au premier caractère qu’elle ne peut pas identifier comme faisant partie intégrante d’un nombre. Il peut s’agir du caractère Null de fin ou bien du premier caractère numérique supérieur ou égal à `base`. Le paramètre de la catégorie `LC_NUMERIC` des paramètres régionaux détermine la reconnaissance du caractère de base dans `nptr`. Pour plus d’informations, consultez [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). `strtoull` et `wcstoull` utilisent les paramètres régionaux actifs ; `_strtoull_l` et `_wcstoull_l` utilisent à la place les paramètres régionaux transmis, mais sont sinon identiques. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n’a pas la valeur `NULL`, un pointeur désignant le caractère qui a arrêté l’analyse est stocké à l’emplacement désigné par `endptr`. Si aucune conversion ne peut être effectuée (aucun chiffre valide n’a été trouvé ou la base spécifiée n’est pas valide), la valeur de `nptr` est stockée à l’emplacement désigné par `endptr`.  
  
 `wcstoull` est une version à caractères larges de `strtoull` et son argument `nptr` est une chaîne de caractères larges. Sinon, ces fonctions se comportent de façon identique.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoull`|`strtoull`|`strtoull`|`wcstoull`|  
|`_tcstoull_l`|`strtoull_l`|`_strtoull_l`|`_wcstoull_l`|  
  
 `strtoull` s’attend à ce que `nptr` pointe vers une chaîne au format suivant :  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; [`letters`]]  
  
 `whitespace` peut être constitué d’espaces et de tabulations, qui sont ignorés ; `digits` se compose d’un ou plusieurs chiffres décimaux ; `letters` comprend une ou plusieurs lettres, de « a » à « z » (ou de « A » à « Z »). Le premier caractère qui ne correspond pas à ce format a pour effet d’arrêter l’analyse. Si `base` a une valeur comprise entre 2 et 36, elle est utilisée comme base numérique. Si `base` a la valeur 0, les premiers caractères de la chaîne désignée par `nptr` servent à déterminer la base. Si le premier caractère est « 0 » et que le deuxième est différent de « x » ou « X », la chaîne est interprétée comme étant un entier octal. Si le premier caractère est « 0 » et que le deuxième est « x » ou « X », la chaîne est interprétée comme étant un entier hexadécimal. Si le premier caractère est un chiffre compris entre « 1 » et « 9 », la chaîne est interprétée comme étant un entier décimal. Les lettres de « a » à « z » (ou de « A » à « Z ») se voient affecter des valeurs comprises entre 10 et 35 ; seules sont autorisées les lettres dont les valeurs affectées sont inférieures à `base`. Le premier caractère situé en dehors de la plage de la base a pour effet d’arrêter l’analyse. Par exemple, si `base` est égal à 0 et que le premier caractère analysé est « 0 », il est supposé qu’il s’agit d’un entier octal et un caractère « 8 » ou « 9 » a pour effet de stopper l’analyse. `strtoull` autorise la présence d’un signe plus (`+`) ou moins (`-`) en guise de préfixe ; la présence d’un signe moins de début indique que le signe de la valeur de retour est inversé.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strtoull`|\<stdlib.h>|  
|`wcstoull`|\<stdlib.h> ou \<wchar.h>|  
|`_strtoull_l`|\<stdlib.h>|  
|`_wcstoull_l`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoll, _strtoll_l, wcstoll, _wcstoll_l](../../c-runtime-library/reference/strtoll-strtoll-l-wcstoll-wcstoll-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)
