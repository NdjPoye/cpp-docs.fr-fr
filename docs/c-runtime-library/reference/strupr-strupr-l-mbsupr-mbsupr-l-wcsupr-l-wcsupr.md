---
title: "_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr | Microsoft Docs"
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
  - "_mbsupr_l"
  - "_mbsupr"
  - "_strupr_l"
  - "_wcsupr"
  - "_wcsupr_l"
  - "_strupr"
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
  - "_mbsupr"
  - "_ftcsupr"
  - "mbsupr"
  - "_tcsupr"
  - "strupr_l"
  - "_fstrupr"
  - "_strupr"
  - "mbsupr_l"
  - "_wcsupr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstrupr (fonction)"
  - "_ftcsupr (fonction)"
  - "_mbsupr (fonction)"
  - "_mbsupr_l (fonction)"
  - "_strupr (fonction)"
  - "_strupr_l (fonction)"
  - "_tcsupr (fonction)"
  - "_tcsupr_l (fonction)"
  - "_wcsupr (fonction)"
  - "_wcsupr_l (fonction)"
  - "convertir la casse, CRT (fonctions)"
  - "fstrupr (fonction)"
  - "ftcsupr (fonction)"
  - "mbsupr (fonction)"
  - "mbsupr_l (fonction)"
  - "conversion de chaînes (C++), casse"
  - "chaînes (C++), casse"
  - "chaînes (C++), convertir la casse"
  - "strupr (fonction)"
  - "strupr_l (fonction)"
  - "tcsupr (fonction)"
  - "tcsupr_l (fonction)"
  - "majuscules, convertir les chaînes en"
  - "wcsupr (fonction)"
  - "wcsupr_l (fonction)"
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en majuscules.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md).  
  
> [!IMPORTANT]
>  `_mbsupr` et `_mbsupr_l` ne peuvent pas être utilisés dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *_strupr(  
   char *str   
);  
wchar_t *_wcsupr(  
   wchar_t *str   
);  
unsigned char *_mbsupr(  
   unsigned char *str   
);  
char *_strupr_l(  
   char *str,  
   _locale_t locale  
);  
wchar_t *_wcsupr_l(  
   wchar_t *str,  
   _locale_t locale  
);  
unsigned char *_mbsupr_l(  
   unsigned char *str,  
   _locale_t locale  
);  
template <size_t size>  
char *_strupr(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wcsupr(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
unsigned char *_mbsupr(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
char *_strupr_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
wchar_t *_wcsupr_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
unsigned char *_mbsupr_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne à mettre en majuscules.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne un pointeur vers la chaîne modifiée.  La modification étant effectuée en place, le pointeur retourné est identique au pointeur passé comme argument d'entrée.  Aucune valeur de retour n'est réservée pour indiquer une erreur.  
  
## Notes  
 La fonction `_strupr` convertit, sur place, toutes les lettres minuscules dans `str` en majuscules.  La conversion est déterminée par le paramètre de catégorie `LC_CTYPE` des paramètres régionaux.  Les autres caractères ne sont pas affectés.  Pour plus d'informations sur `LC_CTYPE`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux actuels; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 `_wcsupr` et `_mbsupr` sont des versions à caractères élargis et à caractères multi\-octets de `_strupr`.  L'argument et la valeur de retour de `_wcsupr` sont des chaînes à caractères larges ; ceux de `_mbsupr` sont des chaînes de caractères multioctets.  Ces trois fonctions se comportent sinon de façon identique.  
  
 Si `str` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent la chaine originale et donnent à `errno` la valeur `EINVAL`.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsupr`|`_strupr`|`_mbsupr`|`_wcsupr`|  
|`_tcsupr_l`|`_strupr_l`|`_mbsupr_l`|`_wcsupr_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strupr`, `_strupr_l`|\<string.h\>|  
|`_wcsupr`, `_wcsupr_l`|\<string.h\> ou \<wchar.h\>|  
|`_mbsupr`, `_mbsupr_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [\_strlwr](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md).  
  
## Équivalent .NET Framework  
 [System::String::ToUpper](https://msdn.microsoft.com/en-us/library/system.string.toupper.aspx)  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)