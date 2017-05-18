---
title: _create_locale, _wcreate_locale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: 23
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 5068d509e335fd99246d5dff5fd51f2b0b1493b6
ms.contentlocale: fr-fr
ms.lasthandoff: 02/28/2017

---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale
Crée un objet de paramètres régionaux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_locale_t _create_locale(  
   int category,  
   const char *locale   
);  
_locale_t _wcreate_locale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `category`  
 Catégorie.  
  
 `locale`  
 Spécificateur de paramètres régionaux.  
  
## <a name="return-value"></a>Valeur de retour  
 Si un `locale` et une `category` valides sont fournis, retourne les paramètres régionaux spécifiés en tant qu’objet `_locale_t`. Les paramètres régionaux actuels du programme ne sont pas modifiés.  
  
## <a name="remarks"></a>Notes  
 La fonction `_create_locale` vous permet de créer un objet qui représente certains paramètres régionaux, pour une utilisation dans des versions régionales de nombreuses fonctions CRT (fonctions avec le suffixe `_l`). Le comportement est semblable à `setlocale`, à ceci près qu’au lieu d’appliquer les paramètres régionaux spécifiés à l’environnement actuel, les paramètres sont enregistrés dans une structure `_locale_t` qui est retournée. La structure `_locale_t` doit être libérée à l’aide de [_free_locale](../../c-runtime-library/reference/free-locale.md) quand elle n’est plus nécessaire.  
  
 `_wcreate_locale` est une version à caractères larges de `_create_locale` ; l'argument `locale` de `_wcreate_locale` est une chaîne à caractères larges. Sinon, `_wcreate_locale` et `_create_locale` se comportent de la même façon.  
  
 L’argument `category` spécifie les parties du comportement relatif aux paramètres régionaux qui sont affectées. Les indicateurs utilisés pour `category` et les parties du programme qu’ils affectent sont indiqués dans le tableau suivant.  
  
 `LC_ALL`  
 Toutes les catégories, comme indiqué ci-dessous.  
  
 `LC_COLLATE`  
 Les fonctions `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` et `wcsxfrm`.  
  
 `LC_CTYPE`  
 Les fonctions de gestion de caractères (sauf `isdigit`, `isxdigit`, `mbstowcs`, et `mbtowc`, qui ne sont pas affectés).  
  
 `LC_MONETARY`  
 Les informations de mise en forme monétaire retournées par la fonction `localeconv`.  
  
 `LC_NUMERIC`  
 Le caractère de virgule décimale pour les routines de sortie mise en forme (comme `printf`), pour les routines de conversion de données, et pour les informations de mise en forme non monétaire retournées par `localeconv`. Outre le caractère de virgule décimale, `LC_NUMERIC` définit le séparateur de milliers et la chaîne de contrôle de regroupement retournés par [localeconv](../../c-runtime-library/reference/localeconv.md).  
  
 `LC_TIME`  
 Les fonctions `strftime` et `wcsftime`.  
  
 Cette fonction valide les paramètres `category` et `locale`. Si le paramètre de catégorie n’est pas une des valeurs indiquées dans le tableau précédent ou que `locale` est `NULL`, la fonction retourne `NULL`.  
  
 L'argument `locale` est un pointeur vers une chaîne qui spécifie les paramètres régionaux. Pour plus d’informations sur le format de l’argument `locale`, consultez [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  
  
 L'argument `locale` peut accepter un nom de paramètres régionaux, une chaîne de langue, une chaîne de langue et un pays/région, une page de codes, ou une chaîne de langue, un pays/région, et une page de codes. L’ensemble des noms de paramètres régionaux, des langues, des pays ou codes zone, et de pages de codes disponibles inclut tous ceux qui sont pris en charge par l’API Windows NLS, à l’exception des pages de codes qui requièrent plus de deux octets par caractère, par exemple, UTF-7 et UTF-8. Si vous fournissez une page de codes comme UTF-7 ou UTF-8, `_create_locale` échoue et retourne NULL. L’ensemble des noms de paramètres régionaux pris en charge par `_create_locale` est décrit dans [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). L’ensemble des chaînes de langue et de pays/région prises en charge par `_create_locale` est répertorié dans [Chaînes de langue](../../c-runtime-library/language-strings.md) et [Chaînes pays/région](../../c-runtime-library/country-region-strings.md).  
  
 Pour plus d’informations sur les paramètres régionaux, consultez [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Le nom précédent de cette fonction, `__create_locale` (avec deux traits de soulignement de début), a été déconseillé.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_create_locale`|\<locale.h>|  
|`_wcreate_locale`|\<locale.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_create_locale.c  
// Sets the current locale to "de-CH" using the  
// setlocale function and demonstrates its effect on the strftime  
// function.  
  
#include <stdio.h>  
#include <locale.h>  
#include <time.h>  
  
int main(void)  
{  
    time_t ltime;  
    struct tm thetime;  
    unsigned char str[100];  
    _locale_t locale;  
  
    // Create a locale object representing the German (Switzerland) locale  
    locale = _create_locale(LC_ALL, "de-CH");  
    time (&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // %#x is the long date representation, appropriate to  
    // the current locale  
    if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
    {
        printf("_strftime_l failed!\n");  
    }
    else  
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);  
    }
  
    _free_locale(locale);  
  
    // Create a locale object representing the default C locale  
    locale = _create_locale(LC_ALL, "C");  
    time(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
    {
        printf("_strftime_l failed!\n");  
    }
    else  
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);  
    }
  
    _free_locale(locale);  
}  
```  
  
```Output  
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'  
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Chaînes de langue](../../c-runtime-library/language-strings.md)   
 [Chaînes pays/région](../../c-runtime-library/country-region-strings.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
