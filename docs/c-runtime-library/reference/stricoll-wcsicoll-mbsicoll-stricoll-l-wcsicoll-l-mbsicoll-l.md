---
title: "_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsicoll_l"
  - "_stricoll_l"
  - "_mbsicoll"
  - "_wcsicoll_l"
  - "_wcsicoll"
  - "_stricoll"
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
  - "stricoll"
  - "_stricoll"
  - "_wcsicoll"
  - "mbsicoll_l"
  - "_mbsicoll"
  - "_ftcsicoll"
  - "wcsicoll_l"
  - "_tcsicoll"
  - "mbsicoll"
  - "stricoll_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsicoll (fonction)"
  - "_mbsicoll (fonction)"
  - "_mbsicoll_l (fonction)"
  - "_stricoll (fonction)"
  - "_stricoll_l (fonction)"
  - "_tcsicoll (fonction)"
  - "_wcsicoll (fonction)"
  - "pages de codes, utiliser pour les comparaisons de chaînes"
  - "ftcsicoll (fonction)"
  - "mbsicoll (fonction)"
  - "mbsicoll_l (fonction)"
  - "stricoll (fonction)"
  - "stricoll_l (fonction)"
  - "comparaison de chaînes (C++), spécifiques à la culture"
  - "chaînes (C++), comparer par page de code"
  - "tcsicoll (fonction)"
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare les chaînes à l'aide d'informations spécifiques aux paramètres régionaux.  
  
> [!IMPORTANT]
>  `_mbsicoll` et `_mbsicoll_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _stricoll(  
   const char *string1,  
   const char *string2   
);  
int _wcsicoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `string1, string2`  
 Chaîne terminée par Null à comparer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne une valeur indiquant la relation de `string1` à `string2`*,* comme suit.  
  
|Valeur de retour|Relation de chaîne1 à chaîne2|  
|----------------------|-----------------------------------|  
|\< 0|`string1` inférieure à `string2`|  
|0|`string1` identique à `string2`|  
|\> 0|`string1` supérieur à `string2`|  
|`_NLSCMPERROR`|Une erreur s'est produite.|  
  
 Chacune de ces fonctions retourne `_NLSCMPERROR`.  Pour utiliser `_NLSCMPERROR`, incluez `STRING.H` ou `MBSTRING.H`.  `_wcsicoll` peut échouer si `string1` ou `string2` contiennent des codes de caractères larges en dehors de la séquence de classement.  Lorsqu'une erreur se produit, `_wcsicoll` peut affecter `errno` à `EINVAL`.  Pour vérifier une erreur lors d'un appel à `_wcsicoll`, affectez `errno` à 0 puis activez `errno` après l'appel de `_wcsicoll`.  
  
## Notes  
 Chacune de ces fonctions exécute une comparaison ne respectant pas la casse de `string1` et `string2` d'après la page de codes en cours d'utilisation.  Ces fonctions doivent être utilisées uniquement lorsqu'il existe une différence entre l'ordre du jeu de caractères et l'ordre des caractères lexicographiques dans la page de codes actuelle et cette différence est intéressante pour la comparaison de chaînes.  
  
 `_stricmp` diffère de `_stricoll` car la comparaison de `_stricmp` est affectée par `LC_CTYPE`, tandis que la comparaison de `_stricoll` est en fonction des catégories `LC_CTYPE` et `LC_COLLATE` des paramètres régionaux.  Pour plus d'informations sur la catégorie `LC_COLLATE`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) et [Catégories de paramètres régionaux](../../c-runtime-library/locale-categories.md).  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux actuels; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Toutes ces fonctions valident leurs paramètres.  Si `string1` ou `string2` sont des pointeurs `NULL` , le gestionnaire des paramètres invalides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsicoll`|`_stricoll`|`_mbsicoll`|`_wcsicoll`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_stricoll`, `_stricoll_l`|\<string.h\>|  
|`_wcsicoll`, `_wcsicoll_l`|&lt;1wchar.h&gt;2, &lt;3string.h&gt;4|  
|`_mbsicoll`, `_mbsicoll_l`|\<mbstring.h\>|  
  
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