---
title: "_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strncoll"
  - "_mbsncoll_l"
  - "_wcsncoll"
  - "_wcsncoll_l"
  - "_mbsncoll"
  - "_strncoll_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbsncoll_l"
  - "strncoll"
  - "_wcsncoll"
  - "_tcsnccoll"
  - "_ftcsnccoll"
  - "wcsncoll"
  - "_mbsncoll"
  - "wcsncoll_l"
  - "strncoll_l"
  - "_ftcsncoll"
  - "_strncoll"
  - "_tcsncoll"
  - "mbsncoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsnccoll (fonction)"
  - "_ftcsncoll (fonction)"
  - "_mbsncoll (fonction)"
  - "_mbsncoll_l (fonction)"
  - "_strncoll (fonction)"
  - "_strncoll_l (fonction)"
  - "_tcsnccoll (fonction)"
  - "_tcsncoll (fonction)"
  - "_wcsncoll (fonction)"
  - "_wcsncoll_l (fonction)"
  - "pages de codes, utiliser pour les comparaisons de chaînes"
  - "ftcsnccoll (fonction)"
  - "ftcsncoll (fonction)"
  - "mbsncoll (fonction)"
  - "mbsncoll_l (fonction)"
  - "chaînes (C++), comparer par page de code"
  - "strncoll (fonction)"
  - "strncoll_l (fonction)"
  - "tcsnccoll (fonction)"
  - "tcsncoll (fonction)"
  - "wcsncoll (fonction)"
  - "wcsncoll_l (fonction)"
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare les chaînes à partir des informations propres aux paramètres régionaux.  
  
> [!IMPORTANT]
>  Les fonctions `_mbsncoll` et `_mbsncoll_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _strncoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsncoll(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strncoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsncoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsncoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `string1, string2`  
 Chaîne terminée par Null à comparer.  
  
 `count`  
 Nombre de caractères à comparer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne une valeur qui indique la relation entre les sous\-chaînes de `string1` et `string2`, comme ci\-dessous.  
  
|Valeur de retour|Relation de chaîne1 à chaîne2|  
|----------------------|-----------------------------------|  
|\< 0|`string1` est inférieur à `string2`.|  
|0|`string1` est identique à `string2`.|  
|\> 0|`string1` est supérieur à `string2`.|  
  
 Chacune de ces fonctions retourne `_NLSCMPERROR`.  Pour utiliser `_NLSCMPERROR`, incluez STRING.h ou MBSTRING.h.  `_wcsncoll` peut échouer si `string1` ou `string2` contient des codes à caractères larges qui se trouvent hors du domaine de l'ordre de tri.  Quand une erreur se produit, `_wcsncoll` peut attribuer à `errno` la valeur `EINVAL`.  Pour rechercher la présence d'une erreur dans un appel à `_wcsncoll`, attribuez à `errno` la valeur 0, puis vérifiez `errno` après avoir appelé `_wcsncoll`.  
  
## Notes  
 Chacune de ces fonctions effectue une comparaison sensible à la casse des `count` premiers caractères de `string1` et `string2`, en fonction de la page de codes en cours d'utilisation.  N'utilisez ces fonctions que s'il existe une différence entre l'ordre du jeu de caractères et l'ordre lexicographique des caractères dans la page de codes, et si cette différence présente un intérêt pour la comparaison de chaînes.  L'ordre du jeu de caractères dépend des paramètres régionaux.  Les versions de ces fonctions qui sont dépourvues du suffixe `_l` utilisent les paramètres régionaux actifs, mais celles qui possèdent le suffixe `_l` utilisent les paramètres régionaux qui sont passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Toutes ces fonctions valident leurs paramètres.  Si `string1` ou `string2` est un pointeur null ou si `count` est supérieur à `INT_MAX`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnccoll`|`_strncoll`|`_mbsncoll`|`_wcsncoll`|  
|`_tcsncoll`|`_strncoll`|[\_mbsnbcoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsncoll`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strncoll`, `_strncoll_l`|\<string.h\>|  
|`_wcsncoll`, `_wcsncoll_l`|\<wchar.h\> ou \<string.h\>|  
|`_mbsncoll`, `_mbsncoll_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)