---
title: "_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l | Microsoft Docs"
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
  - "_mbsnbicoll_l"
  - "_mbsnbcoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbicoll"
  - "mbsnbcoll"
  - "mbsnbicoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
  - "_ftcsnicoll"
  - "_ftcsncoll"
  - "mbsnbcoll_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcoll (fonction)"
  - "_mbsnbcoll_l (fonction)"
  - "_mbsnbicoll (fonction)"
  - "_mbsnbicoll_l (fonction)"
  - "_tcsncoll (fonction)"
  - "_tcsnicoll (fonction)"
  - "mbsnbcoll (fonction)"
  - "mbsnbcoll_l (fonction)"
  - "mbsnbicoll (fonction)"
  - "mbsnbicoll_l (fonction)"
  - "tcsncoll (fonction)"
  - "tcsnicoll (fonction)"
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare `n` octets de deux chaînes de caractères multi\-octets en utilisant les informations de page de codes multi\-octets.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _mbsnbcoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnbicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `string1, string2`  
 Chaînes à comparer.  
  
 `count`  
 Nombre d'octets à comparer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 La valeur de retour indique la relation des sous\-chaînes de `string1` et `string2`.  
  
|Valeur de retour|Description|  
|----------------------|-----------------|  
|\< 0|La sous\-chaîne de `string1` moins que la sous\-chaîne de `string2`.|  
|0|La sous\-chaîne de `string1` identique à la sous\-chaîne de `string2`.|  
|\> 0|La sous\-chaîne de `string1` supérieure à la sous\-chaîne de `string2`.|  
  
 Si `string1` ou `string2` est `NULL` ou si `count` est plus grand que `INT_MAX`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`.  Pour utiliser `_NLSCMPERROR`, incluez STRING.h ou MBSTRING.h.  
  
## Notes  
 Chacune de ces fonctions assemble, au plus, les premiers octets `count` dans `string1` et `string2` et retourne une valeur indiquant la relation entre les sous\-chaînes obtenues de `string1` et `string2`.  Si l'octet final dans la sous\-chaîne de `string1` ou de `string2` est un octet de tête, il n'est pas inclus dans la comparaison ; ces fonctions comparent uniquement les caractères complets dans les sous\-chaînes.  `_mbsnbicoll` est une version de `_mbsnbcoll` ne tenant pas compte des majuscules et des minuscules.  Comme `_mbsnbcmp` et `_mbsnbicmp`, `_mbsnbcoll` et `_mbsnbicoll` assemblent les deux chaînes de caractères multi\-octets selon l'ordre lexicographique spécifié par la [page de codes](../../c-runtime-library/code-pages.md) multi\-octets en cours de utilisation.  
  
 Pour certaines pages de codes et les jeux de caractères correspondants, l'ordre des caractères dans le jeu de caractères peut différer de l'ordre des caractères lexicographiques.  Dans les paramètres régionaux « C », ce n'est pas le cas : l'ordre des caractères dans le jeu de caractères ASCII est le même que l'ordre lexicographique des caractères.  Toutefois, dans certaines pages de codes européennes, par exemple, le caractère « a » \(valeur 0x61\) précède le caractère « ä » \(valeur 0xE4\) dans le jeu de caractères, mais le caractère « ä » précède le caractère « a » lexicographiquement.  Pour effectuer une comparaison lexicographique des chaînes par des octets dans une telle instance, utilisez `_mbsnbcoll` plutôt que `_mbsnbcmp`; pour vérifier que l'égalité de chaîne, utilisez `_mbsnbcmp`.  
  
 Les fonctions `coll` assemblent les chaînes lexicographiquement pour la comparaison, tandis que les fonctions `cmp` testent simplement l'égalité de chaîne, ainsi les fonctions `coll` sont beaucoup plus lentes que les versions correspondantes `cmp`.  Par conséquent, les fonctions `coll` doivent être utilisées uniquement lorsqu'il existe une différence entre l'ordre du jeu de caractères et l'ordre des caractères lexicographiques dans la page de codes actuelle et que cette différence est intéressante pour la comparaison de chaînes.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsncoll`|[\_strncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll`|[\_wcsncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsncoll_l`|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll_l`|[\_wcsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsnicoll`|[\_strnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll`|[\_wcsnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
|`_tcsnicoll_l`|[\_strnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll_l`|[\_wcsnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnbcoll`|\<mbstring.h\>|  
|`_mbsnbcoll_l`|\<mbstring.h\>|  
|`_mbsnbicoll`|\<mbstring.h\>|  
|`_mbsnbicoll_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)