---
title: "strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l | Microsoft Docs"
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
  - "wcscoll"
  - "_mbscoll"
  - "_mbscoll_l"
  - "strcoll"
  - "_strcoll_l"
  - "_wcscoll_l"
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
  - "wcscoll"
  - "_mbscoll"
  - "_tcscoll"
  - "_ftcscoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pages de codes, utiliser pour les comparaisons de chaînes"
  - "mbscoll, fonction"
  - "wcscoll_l, fonction"
  - "ftcscoll, fonction"
  - "wcscoll, fonction"
  - "_strcoll_l, fonction"
  - "tcscoll, fonction"
  - "_ftcscoll, fonction"
  - "_tcscoll, fonction"
  - "_wcscoll_l, fonction"
  - "_mbscoll, fonction"
  - "strcoll_l, fonction"
  - "strcoll, fonctions"
  - "chaînes [C++], comparer par page de codes"
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare des chaînes en utilisant les paramètres régionaux actuels ou une catégorie spécifiée d'état de conversion LC\_COLLATE.  
  
> [!IMPORTANT]
>  `_mbscoll` et `_mbscoll_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int strcoll(  
   const char *string1,  
   const char *string2   
);  
int wcscoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _strcoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale   
);  
int wcscoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale   
);  
int _mbscoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale   
);  
```  
  
#### Paramètres  
 `string1`, `string2`  
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
  
 Chacune de ces fonctions retourne `_NLSCMPERROR` sur une erreur.  Pour utiliser `_NLSCMPERROR`, incluez STRING.H ou MBSTRING.H.  `wcscoll` peut échouer si `string1` ou `string2` sont NULL ou contiennent des codes de caractères larges en dehors de la séquence de classement.  Lorsqu'une erreur se produit, `wcscoll` peut affecter `errno` à `EINVAL`.  Pour vérifier une erreur lors d'un appel à `wcscoll`, affectez `errno` à 0 puis vérifiez `errno` après l'appel de `wcscoll`.  
  
## Notes  
 Chacune de ces fonctions exécute une comparaison tenant compte des majuscules et des minuscules de `string1` et `string2` d'après la page de codes en cours d'utilisation.  Ces fonctions doivent être utilisées uniquement lorsqu'il existe une différence entre l'ordre du jeu de caractères et l'ordre des caractères lexicographiques dans la page de codes actuelle et que cette différence est intéressante pour la comparaison de chaînes.  
  
 Toutes ces fonctions valident leurs paramètres.  Si `string1` ou `string2` est un pointeur null, ou si `count` est supérieur à `INT_MAX`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`.  
  
 La comparaison de deux chaînes est une opération dépendante des paramètres régionaux car tous les paramètres régionaux ont des règles différentes pour classer des caractères.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux du thread actuel pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques à la fonction correspondante sans suffixe mais elles utilisent les paramètres régionaux passés comme paramètre au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strcoll`|\<string.h\>|  
|`wcscoll`|&lt;1wchar.h&gt;2, &lt;3string.h&gt;4|  
|`_mbscoll`, `_mbscoll_l`|\<mbstring.h\>|  
|`_strcoll_l`|\<string.h\>|  
|`_wcscoll_l`|&lt;1wchar.h&gt;2, &lt;3string.h&gt;4|  
  
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