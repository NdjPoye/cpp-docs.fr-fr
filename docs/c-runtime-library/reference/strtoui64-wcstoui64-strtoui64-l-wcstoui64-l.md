---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- _wcstoui64_l
- strtoui64_l
- wcstoui64
- _wcstoui64
- _strtoui64_l
- strtoui64
- _strtoui64
- wcstoui64_l
dev_langs: C++
helpviewer_keywords:
- _strtoui64_l function
- _wcstoui64_l function
- string conversion, to integers
- wcstoui64_l function
- _strtoui64 function
- _wcstoui64 function
- wcstoui64 function
- strtoui64_l function
- strtoui64 function
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1c774473bea1449f5ae1b254d1b98abe8a195d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
Convertit une chaîne en valeur `__int64` non signée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned __int64 _strtoui64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned __int64 _strtoui64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned __int64 _wcstoui64(  
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
 La fonction `_strtoui64` retourne la valeur représentée dans la chaîne `nptr`, sauf dans le cas où la représentation entraînerait un dépassement de capacité positif, auquel cas elle retourne `_UI64_MAX`. `_strtoui64` retourne 0 si aucune conversion ne peut être effectuée.  
  
 `_UI64_MAX` est défini dans LIMITS.H.  
  
 Si `nptr` a la valeur `NULL` ou que `base` est différent de zéro et inférieur à 2 ou supérieur à 36, `errno` prend la valeur `EINVAL`.  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Remarques  
 Le `_strtoui64` fonction convertit `nptr` à un `unsigned` `__int64`. `_wcstoui64` est une version à caractères larges de `_strtoui64` ; son argument `nptr` est une chaîne de caractères larges. Sinon, ces fonctions se comportent de façon identique.  
  
 Les deux fonctions arrêtent de lire la chaîne `nptr` au premier caractère qu’elles ne peuvent pas identifier comme faisant partie intégrante d’un nombre. Il peut s’agir du caractère Null de fin ou bien du premier caractère numérique supérieur ou égal à `base`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoui64`|`_strtoui64`|`_strtoui64`|`_wstrtoui64`|  
|`_tcstoui64_l`|`_strtoui64_l`|`_strtoui64_l`|`_wstrtoui64_l`|  
  
 La valeur du paramètre de catégorie `LC_NUMERIC` des paramètres régionaux actifs détermine la reconnaissance du caractère de base dans `nptr`. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les fonctions sans le suffixe _l utilisent les paramètres régionaux ; `_strtoui64_l` et `_wcstoui64_l` sont identiques aux fonctions correspondantes sans le `_l` suffixe, sauf qu’elles utilisent les paramètres régionaux passé à la place. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
 Si `endptr` n’a pas la valeur `NULL`, un pointeur désignant le caractère qui a arrêté l’analyse est stocké à l’emplacement désigné par `endptr`. Si aucune conversion ne peut être effectuée (aucun chiffre valide n’a été trouvé ou la base spécifiée n’est pas valide), la valeur de `nptr` est stockée à l’emplacement désigné par `endptr`.  
  
 `_strtoui64` s’attend à ce que `nptr` pointe vers une chaîne au format suivant :  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 Un `whitespace` peut être constitué d’espaces et de tabulations, qui sont ignorés ; `digits` se compose d’un ou plusieurs chiffres décimaux. Le premier caractère qui ne correspond pas à ce format a pour effet d’arrêter l’analyse. Si `base` a une valeur comprise entre 2 et 36, elle est utilisée comme base numérique. Si `base` a la valeur 0, les premiers caractères de la chaîne désignée par `nptr` servent à déterminer la base. Si le premier caractère est 0 et que le deuxième est différent de « x » ou « X », la chaîne est interprétée comme étant un entier octal. Si le premier caractère est « 0 » et que le deuxième est « x » ou « X », la chaîne est interprétée comme étant un entier hexadécimal. Si le premier caractère est un chiffre compris entre « 1 » et « 9 », la chaîne est interprétée comme étant un entier décimal. Les lettres de « a » à « z » (ou de « A » à « Z ») se voient affecter des valeurs comprises entre 10 et 35 ; seules sont autorisées les lettres dont les valeurs affectées sont inférieures à `base`. Le premier caractère situé en dehors de la plage de la base a pour effet d’arrêter l’analyse. Par exemple, si `base` est égal à 0 et que le premier caractère analysé est « 0 », il est supposé qu’il s’agit d’un entier octal et un caractère « 8 » ou « 9 » a pour effet de stopper l’analyse.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_strtoui64`|\<stdlib.h>|  
|`_wcstoui64`|\<stdlib.h> ou \<wchar.h>|  
|`_strtoui64_l`|\<stdlib.h>|  
|`_wcstoui64_l`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_strtoui64.c  
#include <stdio.h>  
  
unsigned __int64 atoui64(const char *szUnsignedInt) {  
   return _strtoui64(szUnsignedInt, NULL, 10);  
}  
  
int main() {  
   unsigned __int64 u = atoui64("18446744073709551615");  
   printf( "u = %I64u\n", u );  
}  
```  
  
```Output  
u = 18446744073709551615  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)