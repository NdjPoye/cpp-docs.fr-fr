---
title: "strrchr, wcsrchr, _mbsrchr, _mbsrchr_l | Microsoft Docs"
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
  - "strrchr"
  - "wcsrchr"
  - "_mbsrchr"
  - "_mbsrchr_l"
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
  - "_tcsrchr"
  - "_ftcsrchr"
  - "strrchr"
  - "wcsrchr"
  - "_mbsrchr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsrchr (fonction)"
  - "_mbsrchr (fonction)"
  - "_mbsrchr_l (fonction)"
  - "_tcsrchr (fonction)"
  - "caractères (C++), rechercher"
  - "ftcsrchr (fonction)"
  - "mbsrchr (fonction)"
  - "mbsrchr_l (fonction)"
  - "rechercher dans les chaînes"
  - "chaînes (C++), analyser"
  - "strrchr (fonction)"
  - "tcsrchr (fonction)"
  - "wcsrchr (fonction)"
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strrchr, wcsrchr, _mbsrchr, _mbsrchr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Parcourt une chaîne en cherchant la dernière occurrence d'un caractère.  
  
> [!IMPORTANT]
>  `_mbsrchr` et `_mbsrchr_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *strrchr(  
   const char *str,  
   int c   
); // C only  
char *strrchr(  
   char *str,  
   int c   
); // C++ only  
const char *strrchr(  
   const char *str,  
   int c   
); // C++ only  
wchar_t *wcsrchr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcsrchr(  
   wchar_t *str,  
   wchar_t c   
); // C++ only  
const wchar_t *wcsrchr(  
   const wchar_t *str,  
   wchar_t c   
); // C++ only  
unsigned char *_mbsrchr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbsrchr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbsrchr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbsrchr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only  
unsigned char *_mbsrchr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsrchr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne terminée par Null à trouver.  
  
 `c`  
 Caractère à trouver.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne un pointeur vers la dernière occurrence de `c` dans `str`, ou `NULL` si `c` est introuvable.  
  
## Notes  
 La fonction `strrchr` recherche la dernière occurrence de `c` \(converti en `char`\) dans `str`.  La recherche inclut le caractère null de fin.  
  
 `wcsrchr` et `_mbsrchr` sont des versions à caractères élargis et à caractères multi\-octets de `strrchr`.  Les arguments et la valeur de retour de `wcsrchr`  sont des chaînes à caractères larges ; ceux de `_mbsrchr` sont des chaînes de caractères multioctets.  
  
 En C, ces fonctions acceptent un pointeur `const` comme premier argument.  En C\+\+, deux surcharges sont disponibles.  La surcharge acceptant un pointeur vers `const` retourne un pointeur vers `const` ; la version qui accepte un pointeur vers non\-`const` retourne un pointeur vers non\-`const`.  La macro \_CONST\_CORRECT\_OVERLOADS est définie si les versions `const` et non\-`const` de ces fonctions sont disponibles.  Si vous avez besoin d'un comportement non\-`const` pour les deux surcharges C\+\+, définissez le symbol \_CONST\_RETURN.  
  
 `_mbsrchr` valide ses paramètres.  Si `str` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno`  est défini à `EINVAL`  et  `_mbsrchr`  retourne 0.  `strrchr` et `wcsrchr` ne valident pas leurs paramètres.  Ces trois fonctions se comportent sinon de façon identique.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE`  des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsrchr`|`strrchr`|`_mbsrchr`|`wcsrchr`|  
|**N\/A**|**N\/A**|`_mbsrchr_l`|**N\/A**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strrchr`|\<string.h\>|  
|`wcsrchr`|\<string.h\> ou \<wchar.h\>|  
|`_mbsrchr`, `_mbsrchr_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Pour obtenir un exemple d'utilisation de `strrchr`, consultez [](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md "strchr, wcschr, _mbschr, _mbschr_l").  
  
## Équivalent .NET Framework  
 [System::String::LastIndexOf](https://msdn.microsoft.com/en-us/library/system.string.lastindexof.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)