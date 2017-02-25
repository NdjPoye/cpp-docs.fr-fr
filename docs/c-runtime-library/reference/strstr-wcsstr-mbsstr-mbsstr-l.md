---
title: "strstr, wcsstr, _mbsstr, _mbsstr_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsstr"
  - "wcsstr"
  - "_mbsstr_l"
  - "strstr"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstrstr"
  - "_ftcsstr"
  - "strstr"
  - "wcsstr"
  - "_mbsstr"
  - "_tcsstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrstr (fonction)"
  - "_ftcsstr (fonction)"
  - "_mbsstr (fonction)"
  - "_mbsstr_l (fonction)"
  - "_tcsstr (fonction)"
  - "fstrstr (fonction)"
  - "ftcsstr (fonction)"
  - "mbsstr (fonction)"
  - "mbsstr_l (fonction)"
  - "chaînes (C++), rechercher"
  - "strstr (fonction)"
  - "sous-chaînes, rechercher"
  - "tcsstr (fonction)"
  - "wcsstr (fonction)"
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# strstr, wcsstr, _mbsstr, _mbsstr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Renvoie un pointeur à la première occurrence d'une chaîne recherchée dans une chaîne.  
  
> [!IMPORTANT]
>  `_mbsstr` and `_mbsstr_l` ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne terminée par Null à trouver.  
  
 `strSearch`  
 Chaîne terminée par Null à trouver.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Renvoie un pointeur vers la première occurrence de `strSearch` dans un `str`, ou `NULL` si `strSearch` n'apparaît pas dans `str`.  Si `strSearch` pointe vers une chaîne de longueur nulle, la fonction renvoie `str`.  
  
## Notes  
 La fonction `strstr` renvoie un pointeur vers la première occurrence de `strSearch` dans `str`.  La recherche ne contient pas les caractères de fin null.  `wcsstr` est la version à caractères larges de `strstr` et `_mbsstr` la version à caractères multi\-octets.  Les arguments et la valeur de retour de `wcsstr` sont des chaînes à caractères larges ; ceux de `_mbsstr` sont des chaînes de caractères multioctets.  `_mbsstr` valide ses paramètres.  Si `str` ou `strSearch` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) .  Si l'exécution est autorisée à se poursuivre, `_mbsstr` renvoie 0 et attribue à `errno` la valeur `EINVAL`.  `strstr` et `wcsstr` ne valident pas leurs paramètres.  Ces trois fonctions se comportent sinon de façon identique.  
  
> [!IMPORTANT]
>  Ces fonctions peuvent entraîner une menace de dépassement de mémoire tampon.  Les dépassements de mémoire tampon peuvent être utilisés pour attaquer un système car ils peuvent autoriser l'exécution du code arbitraire, ce qui peut provoquer une augmentation de privilège injustifiée.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 En C, ces fonctions acceptent un pointeur `const` comme premier argument.  En C\+\+, deux surcharges sont disponibles.  La surcharge amenant un pointeur vers `const` renvoie un pointeur vers `const` ; la version qui amène un pointeur vers non\-`const` renvoie un pointeur vers non\-`const`.  La macro \_CONST\_CORRECT\_OVERLOADS est définie si les versions `const` et non\-`const` de ces fonctions sont disponibles.  Si vous avez besoin d'un comportement non\-`const` pour les deux surcharges C\+\+, définissez le symbol \_CONST\_RETURN.  
  
 La valeur de la sortie est affectée par les valeurs de vos paramètres régionaux de `LC_CTYPE` ; consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) pour plus d'informations.  Les versions de ces fonctions n'ayant pas le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant de vos paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**N\/A**|**N\/A**|`_mbsstr_l`|**N\/A**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strstr`|\<string.h\>|  
|`wcsstr`|\<string.h\> ou \<wchar.h\>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h\>|  
  
 Pour plus d'informations à propos de la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
  **Chaîne à analyser.**  
 **Le rapide chien marron sauta au\-dessus du renard paresseux**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**paresseux trouvé à la position 36**   
## Équivalent .NET Framework  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic\_string::find](../Topic/basic_string::find.md)