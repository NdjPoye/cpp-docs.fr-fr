---
title: strtoul, _strtoul_l, wcstoul, _wcstoul_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
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
- strtoul
- _tcstoul
- wcstoul
dev_langs:
- C++
helpviewer_keywords:
- _wcstoul_l function
- _tcstoul function
- _strtoul_l function
- string conversion, to integers
- wcstoul function
- strtoul function
- wcstoul_l function
- strtoul_l function
- tcstoul function
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
caps.latest.revision: 21
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
ms.openlocfilehash: 8916b8645b212f075b9ea575e4bb19e11c5ee975
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="strtoul-strtoull-wcstoul-wcstoull"></a>strtoul, _strtoul_l, wcstoul, _wcstoul_l
Convertit les chaînes en valeur entière de type long non signée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned long strtoul(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long _strtoul_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long wcstoul(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long _wcstoul_l(  
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
 `strtoul` retourne la valeur convertie, le cas échéant, ou `ULONG_MAX` en cas de dépassement de capacité positif. `strtoul` retourne 0 si aucune conversion ne peut être effectuée. `wcstoul` retourne des valeurs de façon analogue à `strtoul`. Pour les deux fonctions, `errno` prend la valeur `ERANGE` si un dépassement de capacité positif ou négatif se produit.  
  
 Pour plus d’informations sur ce code de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions convertit la chaîne d’entrée `nptr` en `unsigned` `long`.  
  
 La fonction `strtoul` arrête de lire la chaîne `nptr` au premier caractère qu’elle ne peut pas identifier comme faisant partie intégrante d’un nombre. Il peut s’agir du caractère Null de fin ou bien du premier caractère numérique supérieur ou égal à `base`. Le paramètre de catégorie `LC_NUMERIC` des paramètres régionaux détermine la reconnaissance du caractère de base dans `nptr`. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). `strtoul` et `wcstoul` utilisent les paramètres régionaux actifs ; `_strtoul_l` et `_wcstoul_l` sont identiques, sauf que ces fonctions utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n’a pas la valeur `NULL`, un pointeur désignant le caractère qui a arrêté l’analyse est stocké à l’emplacement désigné par `endptr`. Si aucune conversion ne peut être effectuée (aucun chiffre valide n’a été trouvé ou la base spécifiée n’est pas valide), la valeur de `nptr` est stockée à l’emplacement désigné par `endptr`.  
  
 `wcstoul` est une version à caractères larges de `strtoul` ; son argument `nptr` est une chaîne de caractères larges. Sinon, ces fonctions se comportent de façon identique.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoul`|`strtoul`|`strtoul`|`wcstoul`|  
|`_tcstoul_l`|`strtoul_l`|`_strtoul_l`|`_wcstoul_l`|  
  
 `strtoul` s’attend à ce que `nptr` pointe vers une chaîne au format suivant :  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 Un `whitespace` peut être constitué d’espaces et de tabulations, qui sont ignorés ; `digits` se compose d’un ou plusieurs chiffres décimaux. Le premier caractère qui ne correspond pas à ce format a pour effet d’arrêter l’analyse. Si `base` a une valeur comprise entre 2 et 36, elle est utilisée comme base numérique. Si `base` a la valeur 0, les premiers caractères de la chaîne désignée par `nptr` servent à déterminer la base. Si le premier caractère est 0 et que le deuxième est différent de « x » ou « X », la chaîne est interprétée comme étant un entier octal. Si le premier caractère est « 0 » et que le deuxième est « x » ou « X », la chaîne est interprétée comme étant un entier hexadécimal. Si le premier caractère est un chiffre compris entre « 1 » et « 9 », la chaîne est interprétée comme étant un entier décimal. Les lettres de « a » à « z » (ou de « A » à « Z ») se voient affecter des valeurs comprises entre 10 et 35 ; seules sont autorisées les lettres dont les valeurs affectées sont inférieures à `base`. Le premier caractère situé en dehors de la plage de la base a pour effet d’arrêter l’analyse. Par exemple, si `base` est égal à 0 et que le premier caractère analysé est « 0 », il est supposé qu’il s’agit d’un entier octal et un caractère « 8 » ou « 9 » a pour effet de stopper l’analyse. `strtoul` autorise la présence d’un signe plus (`+`) ou moins (`-`) en guise de préfixe ; la présence d’un signe moins de début indique que le signe de la valeur de retour est inversé.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strtoul`|\<stdlib.h>|  
|`wcstoul`|\<stdlib.h> ou \<wchar.h>|  
|`_strtoul_l`|\<stdlib.h>|  
|`_wcstoul_l`|\<stdlib.h> ou \<wchar.h>|  
  
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
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)
