---
title: "_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnicoll_l"
  - "_mbsnicoll"
  - "_wcsnicoll_l"
  - "_strnicoll"
  - "_strnicoll_l"
  - "_wcsnicoll"
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
  - "wcshicoll_l"
  - "_ftcsncicoll"
  - "strnicoll_l"
  - "_wcsnicoll"
  - "mbsnicoll_l"
  - "_strnicoll"
  - "mbsnicoll"
  - "_ftcsnicoll"
  - "wcsnicoll"
  - "_tcsnicoll"
  - "_mbsnicoll"
  - "strinicoll"
  - "_tcsncicoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsncicoll (fonction)"
  - "_ftcsnicoll (fonction)"
  - "_mbsnicoll (fonction)"
  - "_mbsnicoll_l (fonction)"
  - "_strnicoll (fonction)"
  - "_strnicoll_l (fonction)"
  - "_tcsncicoll (fonction)"
  - "_tcsnicoll (fonction)"
  - "_wcsnicoll (fonction)"
  - "_wcsnicoll_l (fonction)"
  - "pages de codes, utiliser pour les comparaisons de chaînes"
  - "ftcsncicoll (fonction)"
  - "ftcsnicoll (fonction)"
  - "mbsnicoll (fonction)"
  - "mbsnicoll_l (fonction)"
  - "chaînes (C++), comparer par page de code"
  - "strnicoll (fonction)"
  - "strnicoll_l (fonction)"
  - "tcsncicoll (fonction)"
  - "tcsnicoll (fonction)"
  - "wcsnicoll (fonction)"
  - "wcsnicoll_l (fonction)"
ms.assetid: abf0c569-725b-428d-9ff2-924f430104b4
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare les chaînes à l'aide d'informations spécifiques aux paramètres régionaux.  
  
> [!IMPORTANT]
>  `_mbsnicoll` et `_mbsnicoll_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _strnicoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicoll(  
   const wchar_t *string1,  
   const wchar_t *string2 ,  
   size_t count   
);  
int _mbsnicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2 ,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `string1, string2`  
 Chaînes terminées par Null à comparer.  
  
 `count`  
 Nombre de caractères à comparer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne une valeur indiquant la relation des sous\-chaînes de `string1` et `string2`*,* comme suit.  
  
|Valeur de retour|Relation de chaîne1 à chaîne2|  
|----------------------|-----------------------------------|  
|\< 0|`string1` inférieure à `string2`|  
|0|`string1` identique à `string2`|  
|\> 0|`string1` supérieur à `string2`|  
  
 Chacune de ces fonctions retourne `_NLSCMPERROR`.  Pour utiliser `_NLSCMPERROR`, incluez STRING.H ou MBSTRING.H.  `_wcsnicoll` peut échouer si `string1` ou `string2` contiennent des codes de caractères larges en dehors du domaine de la séquence de classement.  Lorsqu'une erreur se produit, `_wcsnicoll` peut affecter `errno` à `EINVAL`.  Pour vérifier une erreur lors d'un appel à `_wcsnicoll`, affectez `errno` à 0 puis vérifiez `errno` après l'appel de `_wcsnicoll`**.**  
  
## Notes  
 Chacune de ces fonctions exécute une comparaison des premiers caractères `count` dans `string1` et `string2` selon la page de codes, sans tenir compte des majuscules ou des minuscules.  Ces fonctions doivent être utilisées uniquement lorsqu'il existe une différence entre l'ordre du jeu de caractères et l'ordre des caractères lexicographiques dans la page de codes et que cette différence est intéressante pour la comparaison de chaînes.  Les versions de ces fonctions sans suffixe `_l` utilisent les paramètres régionaux et la page de codes actuelle.  Les versions avec le suffixe`_l` sont identiques mais elles utilisent les paramètres régionaux passés à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Toutes ces fonctions valident leurs paramètres.  Si `string1` ou `string2` est un pointeur null, ou si le compte est supérieur à `INT_MAX`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`**.**  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsncicoll`|`_strnicoll`|`_mbsnbicoll`|`_wcsnicoll`|  
|`_tcsnicoll`|`_strnicoll`|[\_mbsnbicoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsnicoll`|  
|`_tcsnicoll_l`|`_strnicoll_l`|`_mbsnbicoll_l`|`_wcsnicoll_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strnicoll`, `_strnicoll_l`|\<string.h\>|  
|`_wcsnicoll`, `_wcsnicoll_l`|\<string.h\> ou \<wchar.h\>|  
|`_mbsnicoll`, `_mbsnicoll_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
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