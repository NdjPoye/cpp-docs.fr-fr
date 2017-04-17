---
title: "strcmp, wcscmp, _mbscmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscmp"
  - "_mbscmp"
  - "strcmp"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbscmp"
  - "wcscmp"
  - "strcmp"
  - "_tcscmp"
  - "_ftcscmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcscmp (fonction)"
  - "_mbscmp (fonction)"
  - "_tcscmp (fonction)"
  - "ftcscmp (fonction)"
  - "mbscmp (fonction)"
  - "strcmp (fonction)"
  - "comparaison de chaînes (C++)"
  - "chaînes (C++), comparer"
  - "tcscmp (fonction)"
  - "wcscmp (fonction)"
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# strcmp, wcscmp, _mbscmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Comparer des chaînes.  
  
> [!IMPORTANT]
>  `_mbscmp` ne peut pas être utilisée dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int strcmp(  
   const char *string1,  
   const char *string2   
);  
int wcscmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
```  
  
#### Paramètres  
 `string1`, `string2`  
 Chaîne terminée par Null à comparer.  
  
## Valeur de retour  
 La valeur de retour pour chacune de ces fonctions indique la relation ordinale de `string1` avec `string2`.  
  
|Valeur|Relation de chaîne1 à chaîne2|  
|------------|-----------------------------------|  
|\< 0|`string1` est inférieur à `string2`|  
|0|`string1` est identique à `string2`|  
|\> 0|`string1` est supérieur à `string2`|  
  
 En cas d'erreur de validation d'un paramètre, `_mbscmp` retourne `_NLSCMPERROR`, qui est défini dans \<string.h\> et dans \<mbstring.h\>.  
  
## Notes  
 La fonction `strcmp` effectue une comparaison ordinale de `string1` et de `string2`, et retourne une valeur qui indique leur relation.  `wcscmp` et `_mbscmp` sont respectivement des versions à caractères larges et à caractères multioctets de `strcmp`.  `_mbscmp` reconnaît les séquences de caractères multioctets selon la page de codes multioctets active et retourne `_NLSCMPERROR` en cas d'erreur.  Pour plus d'informations, consultez [Pages de codes](../../c-runtime-library/code-pages.md).  En outre, si `string1` ou `string2` est un pointeur null, `_mbscmp` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, `_mbscmp` retourne `_NLSCMPERROR` et définit `errno` à `EINVAL`.  `strcmp` et `wcscmp` ne vérifient pas leurs paramètres.  Ces trois fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcscmp`|`strcmp`|`_mbscmp`|`wcscmp`|  
  
 Les fonctions `strcmp` diffèrent des fonctions `strcoll` en ceci que les comparaisons `strcmp` sont ordinales et ne sont pas affectées par les paramètres régionaux.  `strcoll` compare les chaînes d'un point de vue lexicographique en utilisant la catégorie `LC_COLLATE` des paramètres régionaux actuels.  Pour plus d'informations sur la catégorie `LC_COLLATE`, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Dans les paramètres régionaux "C", l'ordre des caractères du jeu de caractères \(jeu de caractères ASCII\) est le même que l'ordre lexicographique des caractères.  Cependant, dans d'autres paramètres régionaux, l'ordre des caractères du jeu de caractères peut différer de l'ordre lexicographique.  Par exemple, dans certains paramètres régionaux européens, le caractère « a » \(valeur 0 x 61\) se trouve avant le caractère « ä » \(valeur 0xE4\) dans le jeu de caractères, mais le caractère « ä » se trouve avant le caractère « a » d'un point de vue lexicographique.  
  
 Dans les paramètres régionaux pour lesquels le jeu de caractères et l'ordre lexicographique des caractères diffèrent, vous pouvez utiliser `strcoll` au lieu de `strcmp` pour la comparaison lexicographique de chaînes.  Vous pouvez aussi utiliser `strxfrm` sur les chaînes d'origine, puis utiliser `strcmp` sur les chaînes résultantes.  
  
 Les fonctions `strcmp` respectent la casse.  `_stricmp`, `_wcsicmp` et `_mbsicmp` comparent les chaînes en les convertissant d'abord en minuscules.  Deux chaînes contenant des caractères qui se trouvent entre « Z » et « a » dans la table ASCII \(« \[ », « `\` », « \] », « `^` », « `_` » et « ``` »\) se comparent différemment, en fonction de leur casse.  Par exemple, les deux chaînes `"ABCDE"` et `"ABCD^"` se comparent d'un certaine façon si la comparaison est en minuscules \(`"abcde"` \> `"abcd^"`\) et d'une autre façon \(`"ABCDE"` \< `"ABCD^"`\) si la comparaison est en majuscules.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strcmp`|\<string.h\>|  
|`wcscmp`|\<string.h\> ou \<wchar.h\>|  
|`_mbscmp`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_strcmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof (tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
  **Chaînes à comparer :**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown dog jumps over the lazy fox**  
 **strcmp : chaîne 1 est supérieure à chaîne 2**  
 **\_stricmp : chaîne 1 est égale à chaîne 2**   
## Équivalent .NET Framework  
 [System::String::CompareOrdinal](https://msdn.microsoft.com/en-us/library/system.string.compareordinal.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [\_memicmp, \_memicmp\_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)