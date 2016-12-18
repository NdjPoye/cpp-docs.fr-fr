---
title: "_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l | Microsoft Docs"
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
  - "_wcsnicmp"
  - "_strnicmp_l"
  - "_wcsnicmp_l"
  - "_strnicmp"
  - "_mbsnicmp"
  - "_mbsnicmp_l"
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
  - "wcsnicmp_l"
  - "_strnicmp"
  - "_ftcsnicmp"
  - "mbsnicmp_l"
  - "_ftcsncicmp"
  - "mbsnicmp"
  - "_tcsncicmp"
  - "_mbsnicmp"
  - "_tcsnicmp"
  - "strnicmp_l"
  - "_wcsnicmp"
  - "_wcsnicmp_l"
  - "CORECRT_WSTRING/_wcsnicmp"
  - "CORECRT_WSTRING/_wcsnicmp_l"
  - "string/_strnicmp"
  - "string/_strnicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsncicmp (fonction)"
  - "_ftcsnicmp (fonction)"
  - "_mbsnicmp (fonction)"
  - "_mbsnicmp_l (fonction)"
  - "_strnicmp (fonction)"
  - "_strnicmp_l (fonction)"
  - "_tcsncicmp (fonction)"
  - "_tcsnicmp (fonction)"
  - "_wcsnicmp (fonction)"
  - "_wcsnicmp_l (fonction)"
  - "caractères (C++), comparer"
  - "ftcsncicmp (fonction)"
  - "ftcsnicmp (fonction)"
  - "mbsnicmp (fonction)"
  - "mbsnicmp_l (fonction)"
  - "comparaison de chaînes (C++), minuscules"
  - "comparaison de chaînes (C++), strncmp (fonction)"
  - "chaînes (C++), comparer des caractères de"
  - "strncmp (fonction)"
  - "strnicmp_l (fonction)"
  - "tcsncicmp (fonction)"
  - "tcsnicmp (fonction)"
  - "wcsnicmp (fonction)"
  - "wcsnicmp_l (fonction)"
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare le nombre spécifié de caractères de deux chaînes sans tenir compte de la casse.  
  
> [!IMPORTANT]
>  Les fonctions `_mbsnicmp` et `_mbsnicmp_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _strnicmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsnicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicmp_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicmp_l(  
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
 Indique la relation entre les sous\-chaînes, comme suit.  
  
|Valeur de retour|Description|  
|----------------------|-----------------|  
|\< 0|La sous\-chaîne de `string1` est inférieure à la sous\-chaîne de `string2`.|  
|0|La sous\-chaîne de `string1` est identique à la sous\-chaîne de `string2`.|  
|\> 0|La sous\-chaîne de `string1` est supérieure à la sous\-chaîne de `string2`.|  
  
 En cas d'erreur de validation de paramètre, ces fonctions retournent `_NLSCMPERROR`, qui est défini dans \<string.h\> et dans \<mbstring.h\>.  
  
## Notes  
 La fonction ordinale `_strnicmp` compare, au plus, les premiers `count` caractères de `string1` et de `string2`.  La comparaison est effectuée sans tenir compte de la casse, en convertissant chaque caractère en minuscule.  `_strnicmp` est une version de `strncmp` respectant la casse.  La comparaison se termine si un caractère null de fin est atteint dans l'une ou l'autre des chaînes avant que `count` caractères soient comparés.  Si les chaînes sont égales quand un caractère null de fin est atteint dans l'une ou l'autre des chaînes avant que `count` caractères soient comparés, la chaîne la plus courte est considérée comme étant inférieure.  
  
 Les caractères de 91 à 96 de la table ASCII \(« \[ », « \\ », « \] », « ^ », « \_ » et « ' »\) sont évalués comme étant inférieurs à n'importe quel caractère alphabétique.  Ce classement est identique à celui de `stricmp`.  
  
 `_wcsnicmp` et `_mbsnicmp` sont des versions à caractères larges et à caractères multioctets de `_strnicmp`.  Les arguments de `_wcsnicmp` sont des chaînes de caractères larges ; ceux de `_mbsnicmp` sont des chaînes de caractères multioctets.  `_mbsnicmp` reconnaît les séquences de caractères multioctets selon la page de codes multioctets active et retourne `_NLSCMPERROR` en cas d'erreur.  Pour plus d'informations, consultez [Pages de codes](../../c-runtime-library/code-pages.md).  Ces trois fonctions se comportent sinon de façon identique.  Ces fonctions sont affectées par les paramètres régionaux : les versions qui n'ont pas le suffixe `_l` utilisent les paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux et les versions qui ont le suffixe `_l` utiliser le paramètre `locale` qui est passé en entrée.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Toutes ces fonctions valident leurs paramètres.  Si `string1` ou `string2` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsncicmp`|`_strnicmp`|`_mbsnicmp`|`_wcsnicmp`|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsncicmp_l`|`_strnicmp_l`|`_mbsnicmp_l`|`_wcsnicmp_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strnicmp`, `_strnicmp_l`|\<string.h\>|  
|`_wcsnicmp`, `_wcsnicmp_l`|\<string.h\> ou \<wchar.h\>|  
|`_mbsnicmp`, `_mbsnicmp_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md).  
  
## Équivalent .NET Framework  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)