---
title: "strspn, wcsspn, _mbsspn, _mbsspn_l | Microsoft Docs"
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
  - "_mbsspn_l"
  - "wcsspn"
  - "strspn"
  - "_mbsspn"
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
  - "_ftcsspn"
  - "wcsspn"
  - "_mbsspn"
  - "_tcsspn"
  - "strspn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsspn (fonction)"
  - "_mbsspn (fonction)"
  - "_mbsspn_l (fonction)"
  - "_tcsspn (fonction)"
  - "ftcsspn (fonction)"
  - "mbsspn (fonction)"
  - "mbsspn_l (fonction)"
  - "chaînes (C++), rechercher"
  - "strspn (fonction)"
  - "sous-chaînes, rechercher"
  - "tcsspn (fonction)"
  - "wcsspn (fonction)"
ms.assetid: d077284a-809f-4068-959e-c6d6262677eb
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strspn, wcsspn, _mbsspn, _mbsspn_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne l'index du premier caractère, dans une chaîne, qui ne fait pas partie d'un jeu de caractères.  
  
> [!IMPORTANT]
>  `_mbsspn` et `_mbsspn_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
size_t strspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcsspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbsspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbsspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `str`  
 Chaîne terminée par Null à trouver.  
  
 `strCharSet`  
 Jeu de caractères se terminant par null.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne une valeur entière spécifiant la longueur de la sous\-chaîne dans `str` qui représentent exclusivement des caractères dans `strCharSet`*.* Si `str` commence par un caractère pas dans `strCharSet`*,* la fonction retourne 0.  
  
## Notes  
 La fonction `strspn` retourne l'index du premier caractère dans `str` qui n'appartient pas au jeu de caractères dans `strCharSet`.  La recherche ne contient pas les caractères de fin null.  
  
 `wcsspn` et `_mbsspn` sont des versions à caractères larges et à caractères multi\-octets de  `strspn`**.** Les arguments de `wcsspn` sont des chaînes à caractères larges ; ceux de `_mbsspn` sont des chaînes de caractères multi\-octets.  `_mbsspn` valide ses paramètres.  Si `str` ou `strCharSet` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) .  Si l'exécution est autorisée à se poursuivre, `_mbspn` renvoie 0 et attribue à `errno` la valeur `EINVAL`.  `strspn` et `wcsspn` ne valident pas leurs paramètres.  Ces trois fonctions se comportent sinon de façon identique.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsspn`|`strspn`|`_mbsspn`|`wcsspn`|  
|**N\/A**|**N\/A**|`_mbsspn_l`|**N\/A**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strspn`|\<string.h\>|  
|`wcsspn`|\<string.h\> ou \<wchar.h\>|  
|`_mbsspn`, `_mbsspn_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strspn.c  
// This program uses strspn to determine  
// the length of the segment in the string "cabbage"  
// consisting of a's, b's, and c's. In other words,  
// it finds the first non-abc letter.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[] = "cabbage";  
   int  result;  
   result = strspn( string, "abc" );  
   printf( "The portion of '%s' containing only a, b, or c "  
           "is %d bytes long\n", string, result );  
}  
```  
  
  **La partie « chou » contenant uniquement a, b, ou c est de 5 octets**   
## Équivalent .NET Framework  
 [System::String::Substring](https://msdn.microsoft.com/en-us/library/system.string.substring.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strspnp, \_wcsspnp, \_mbsspnp, \_mbsspnp\_l](../../c-runtime-library/reference/strspnp-wcsspnp-mbsspnp-mbsspnp-l.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)