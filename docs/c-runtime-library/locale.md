---
title: "Param&#232;tres r&#233;gionaux | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "informations sur le pays"
  - "routines des informations relatives aux langues"
  - "routines des paramètres régionaux"
  - "localisation, paramètres régionaux"
  - "setlocale (fonction)"
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Param&#232;tres r&#233;gionaux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*Les paramètres régionaux* font référence au paramètres de pays\/région et de langue que vous pouvez utiliser pour personnaliser votre programme.  Certaines catégories dépendant des paramètres régionaux incluent le format d'affichage des dates et des valeurs monétaires.  Pour plus d'informations, consultez [Catégories de paramètres régionaux](../c-runtime-library/locale-categories.md).  
  
 Utilisez la fonction [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) afin de modifier ou d'envoyer une requête à certains ou tout les programmes en cours ou les threads de paramètres régionaux durant l'exécution de fonctions sans le suffixe `_l`.  Les fonctions possédant le suffixe `_l` utiliseront les paramètres régionaux de leurs informations de paramètres régionaux uniquement pendant l'exécution de cette fonction spécifique.  Pour créer des paramètres régionaux afin qu'une fonction ayant un suffixe `_l` puisse les utiliser, utilisez [\_create\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md).  Pour libérer ces paramètres régionaux, utilisez [\_free\_locale](../c-runtime-library/reference/free-locale.md).  Pour obtenir les paramètres régionaux actuels, utilisez [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md).  
  
 Utilisez [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) pour déterminer si chaque thread possède ses propres paramètres régionaux, ou si tous les threads d'un programme partagent les mêmes paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux et pages de codes](../text/locales-and-code-pages.md).  
  
 Des versions plus sécurisées des fonctions du tableau suivant sont disponibles, elles sont indiquées par le suffixe `_s` \(« sécurisé »\).  Pour plus d'informations, consultez [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md).  
  
### routines dépendantes des paramètres régionaux  
  
|Routine|Utilisation|dépendance de paramètre de catégorie d'`setlocale`|  
|-------------|-----------------|--------------------------------------------------------|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Convertissez un caractère en valeur à virgule flottante|`LC_NUMERIC`|  
|[atoi, \_atoi\_l, \_wtoi, \_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Convertissez un caractère en valeur entière|`LC_NUMERIC`|  
|[\_atoi64, \_atoi64\_l, \_wtoi64, \_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Convertissez un caractère en une valeur entière 64 bits|`LC_NUMERIC`|  
|[atol, \_atol\_l, \_wtol, \_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Convertissez un caractère en une valeur longue|`LC_NUMERIC`|  
|[\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Convertissez un caractère en une valeur double\-long|`LC_NUMERIC`|  
|[is routines](../c-runtime-library/is-isw-routines.md)|Testez un entier donné pour un état particulier.|`LC_CTYPE`|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Testez l'octet de tête|`LC_CTYPE`|  
|[localeconv](../c-runtime-library/reference/localeconv.md)|Lisez les valeurs appropriées pour formatter des quantités numériques|`LC_MONETARY, LC_NUMERIC`|  
|[MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)|Longueur maximale en octets de tout caractère multioctets dans les paramètres régionaux actifs \(macro définie dans STDLIB.H\)|`LC_CTYPE`|  
|[\_mbccpy, \_mbccpy\_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Copiez un caractère multioctets|`LC_CTYPE`|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Validez et retournez le nombre d'octets dans un caractère multioctets|`LC_CTYPE`|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Pour les chaînes de caractères multioctets : validez chaque caractère de la chaîne ; retournez la longueur de chaîne|`LC_CTYPE`|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Convertissez la séquence de caractères multioctets à la séquence correspondante de caractères larges|`LC_CTYPE`|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Convertissez le caractère multioctets au caractère élargi correspondant|`LC_CTYPE`|  
|Fonctions [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|Ecrivez une sortie mise en forme|`LC_NUMERIC` \(détermine la sortie de caractères de base\)|  
|fonctions [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|Lisez une entrée mise en forme|`LC_NUMERIC` \(détermine la reconnaissance de caractères de base\)|  
|[setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|Sélectionnez les paramètres régionaux du programme|Non applicable|  
|[strcoll, wcscoll, \_mbscoll, \_strcoll\_l, \_wcscoll\_l, \_mbscoll\_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Compare les caractères de deux chaînes|`LC_COLLATE`|  
|[\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Compare deux chaînes sans tenir compte du cas|`LC_CTYPE`|  
|[\_stricoll, \_wcsicoll, \_mbsicoll, \_stricoll\_l, \_wcsicoll\_l, \_mbsicoll\_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Comparez les caractères de deux chaînes \(insensible à la casse\)|`LC_COLLATE`|  
|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Comparez les `n` premiers caractères de deux chaînes|`LC_COLLATE`|  
|[\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Comparez les caractères de deux chaînes sans tenir compte du cas.|`LC_CTYPE`|  
|[\_strnicoll, \_wcsnicoll, \_mbsnicoll, \_strnicoll\_l, \_wcsnicoll\_l, \_mbsnicoll\_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Comparez les `n` premiers caractères de deux chaînes \(insensible à la casse\)|`LC_COLLATE`|  
|[strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Formattez la valeur de la date et de l'heure en fonction de l'argument `format` fourni|`LC_TIME`|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Convertissez, en place, chaque lettre majuscule dans la chaîne spécifiée en minuscules|`LC_CTYPE`|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Convertissez une chaîne de caractères en une valeur `double`.|`LC_NUMERIC` \(détermine la reconnaissance de caractères de base\)|  
|[strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Convertissez une chaîne de caractères en une valeur `long`.|`LC_NUMERIC` \(détermine la reconnaissance de caractères de base\)|  
|[strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Convertissez une chaîne de caractères en une valeur longue non signée|`LC_NUMERIC` \(détermine la reconnaissance de caractères de base\)|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Convertissez, en place, chaque lettre minuscule de la chaîne spécifiée en majuscules|`LC_CTYPE`|  
|[strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Transformez la chaîne en forme compilée en respectant les paramètres régionaux|`LC_COLLATE`|  
|[tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Convertissez le caractère donné en la minuscule correspondante|`LC_CTYPE`|  
|[toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Convertissez le caractère donné en la lettre majuscule correspondante|`LC_CTYPE`|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Convertissez la séquence de caractères larges à la séquence correspondante de caractères multioctets|`LC_CTYPE`|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Convertissez le caractère élargi au caractère multioctets correspondant|`LC_CTYPE`|  
  
> [!NOTE]
>  Pour les routines multioctets, la page de codes multioctets doit être équivalente aux paramètres régionaux définis avec [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  [\_setmbcp](../c-runtime-library/reference/setmbcp.md), avec un argument `_MB_CP_LOCALE`, rend la page de codes multioctets identique à la page de codes `setlocale`.  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)