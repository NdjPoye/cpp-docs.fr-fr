---
title: "_create_locale, _wcreate_locale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_create_locale"
  - "__create_locale"
  - "_wcreate_locale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "create_locale"
  - "_create_locale"
  - "__create_locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__create_locale (fonction)"
  - "_create_locale (fonction)"
  - "create_locale (fonction)"
  - "paramètres régionaux, créer"
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _create_locale, _wcreate_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un objet local.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `category`  
 Catégorie.  
  
 `locale`  
 Spécificateur de paramètres régionaux.  
  
## Valeur de retour  
 Si un `locale` valide et `category` sont spécifiés, renvoie les paramètres régionaux spécifiés comme un objet `_locale_t` .  Les paramètres régionaux actuels du programme ne sont pas modifiés.  
  
## Notes  
 La fonction `_create_locale` vous permet de créer un objet qui représente certains paramètres spécifiques à une région, pour une utilisation dans des versions régionales de nombreuses fonctions CRT \(fonctions avec le suffixe `_l` \).  Le comportement est semblable à `setlocale`, mais au lieu d'appliquer des paramètres régionaux spécifiés à l'environnement actuel, les paramètres sont stockés dans une structure `_locale_t` qui est retournée.  La structure `_locale_t` doit être libérée avec [\_free\_locale](../../c-runtime-library/reference/free-locale.md) devenu inutile.  
  
 `_wcreate_locale` est une version à caractères larges de `_create_locale`; l'argument `locale` vers `_wcreate_locale` est une chaîne à caractères larges.  `_wcreate_locale` et `_create_locale` se comportent sinon de manière identique.  
  
 L'argument `category` spécifie les parties du comportement spécifique aux paramètres régionaux affectés.  Les indicateurs utilisés pour `category` et les parties du programme qu'elles affectent sont comme indiqué dans le tableau suivant.  
  
 `LC_ALL`  
 Toutes les catégories, comme répertoriées ci\-dessous.  
  
 `LC_COLLATE`  
 Les fonctions `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll`, et `wcsxfrm`.  
  
 `LC_CTYPE`  
 Les fonctions de gestion de caractères \(sauf `isdigit`, `isxdigit`, `mbstowcs`, et `mbtowc`, qui ne sont pas affectés\).  
  
 `LC_MONETARY`  
 Les informations de mise en forme monétaire retournées par la fonction `localeconv`.  
  
 `LC_NUMERIC`  
 Le caractère de virgule décimale pour les routines de sortie mise en forme \(comme `printf`\), pour les routines de conversion de données, et pour les informations de mise en forme non monétaire retournées par `localeconv`.  Outre le caractère de virgule décimale, `LC_NUMERIC` définit le séparateur de milliers et la chaîne de contrôle de regroupement retournés par [localeconv](../../c-runtime-library/reference/localeconv.md).  
  
 `LC_TIME`  
 Les fonctions `strftime` et `wcsftime`.  
  
 Cette fonction valide les paramètres `category` et `locale`.  Si le paramètre Catégorie ne fait pas partie des valeurs données dans la table précédente ou si `locale` est `NULL`, la fonction renvoie `NULL`.  
  
 L'argument `locale` est un pointeur vers une chaîne qui spécifie les paramètres régionaux.  Pour plus d'informations sur le format de l'argument `locale`, consultez [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  
  
 L'argument `locale` peut accepter un nom de paramètres régionaux, une chaîne de langue, une chaîne de langue et un pays\/région, une page de code, ou une chaîne de langue, un pays\/région, et une page de codes.  L'ensemble des noms de paramètres régionaux, des langages, des codes pays ou codes zone, et des pages de codes disponibles incluent tous ceux pris en charge par l'API Windows NLS, à l'exception des pages de codes qui requièrent plus de deux octets par caractère—par exemple, UTF\-7 et UTF\-8.  Si vous fournissez une page de codes comme UTF\-7 ou UTF\-8, `_create_locale` va échouer et renvoyer Null.  L'ensemble des noms de paramètres régionaux pris en charge par `_create_locale` sont décrits dans [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  L'ensemble des chaînes de langage et de pays\/région prises en charge par `_create_locale` sont répertoriées dans [Chaînes de langue](../../c-runtime-library/language-strings.md) et [Chaînes pays\/région](../../c-runtime-library/country-region-strings.md).  
  
 Pour plus d'informations sur ces paramètres régionaux, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Ancien nom de cette fonction, `__create_locale` \(avec deux principaux traits de soulignement\), a été déconseillé.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_create_locale`|\<locale.h\>|  
|`_wcreate_locale`|\<locale.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
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
       //  
       if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
               printf("_strftime_l failed!\n");  
       else  
               printf("In de-CH locale, _strftime_l returns '%s'\n",   
                      str);  
  
       _free_locale(locale);  
  
       // Create a locale object representing the default C locale  
       locale = _create_locale(LC_ALL, "C");  
       time (&ltime);  
       _gmtime64_s(&thetime, &ltime);  
  
       if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
               printf("_strftime_l failed!\n");  
       else  
               printf("In 'C' locale, _strftime_l returns '%s'\n",   
                      str);  
  
       _free_locale(locale);  
}  
```  
  
## Résultat de l'exemple  
  
```  
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'  
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'  
```  
  
## Équivalent .NET Framework  
 [System::Globalization::CultureInfo Class](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)  
  
## Voir aussi  
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Chaînes de langue](../../c-runtime-library/language-strings.md)   
 [Chaînes pays\/région](../../c-runtime-library/country-region-strings.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)   
 [\_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)