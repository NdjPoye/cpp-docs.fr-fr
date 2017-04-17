---
title: "strncmp, wcsncmp, _mbsncmp, _mbsncmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strncmp"
  - "_mbsncmp"
  - "wcsncmp"
  - "_mbsncmp_l"
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
  - "_ftcsnccmp"
  - "_ftcsncmp"
  - "_tcsncmp"
  - "_tcsnccmp"
  - "strncmp"
  - "_mbsncmp"
  - "wcsncmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsnccmp (fonction)"
  - "_ftcsncmp (fonction)"
  - "_mbsncmp (fonction)"
  - "_mbsncmp_l (fonction)"
  - "_tcsnccmp (fonction)"
  - "_tcsncmp (fonction)"
  - "caractères (C++), comparer"
  - "ftcsnccmp (fonction)"
  - "ftcsncmp (fonction)"
  - "mbsncmp (fonction)"
  - "mbsncmp_l (fonction)"
  - "comparaison de chaînes (C++), strncmp (fonction)"
  - "chaînes (C++), comparer des caractères de"
  - "strncmp (fonction)"
  - "tcsnccmp (fonction)"
  - "tcsncmp (fonction)"
  - "wcsncmp (fonction)"
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# strncmp, wcsncmp, _mbsncmp, _mbsncmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare jusqu'au nombre spécifié de caractères de deux chaînes.  
  
> [!IMPORTANT]
>  `_mbsncmp` et `_mbsncmp_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime.  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int strncmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int wcsncmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsncmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,   
   _locale_t locale  
);int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### Paramètres  
 `string1, string2`  
 Chaînes à comparer.  
  
 `count`  
 Nombre de caractères à comparer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 La valeur de retour indique la relation des sous\-chaînes de `string1` et de `string2` comme suit.  
  
|Valeur de retour|Description|  
|----------------------|-----------------|  
|\< 0|sous\-chaîne de `string1` inférieure à sous\-chaîne de `string2`|  
|0|sous\-chaîne de `string1` identique à sous\-chaîne de `string2`|  
|\> 0|sous\-chaîne de `string1` supérieure à sous\-chaîne de `string2`|  
  
 En cas d'erreur de validation d'un paramètre, `_mbsncmp` et `_mbsncmp_l` retournent `_NLSCMPERROR`, qui est défini dans \<string.h\> et dans \<mbstring.h\>.  
  
## Notes  
 La fonction `strncmp` effectue une comparaison ordinale d'au moins les `count` caractères de `string1` et de `string2`, et retourne une valeur qui indique la relation entre les sous\-chaînes.  `strncmp` est une version respectant la casse de `_strnicmp`.  `wcsncmp` et `_mbsncmp` sont des versions respectant la casse de `_wcsnicmp` et de `_mbsnicmp`.  
  
 `wcsncmp` et `_mbsncmp` sont des versions à caractères larges et à caractères multioctets de `strncmp`.  Les arguments de `wcsncmp` sont des chaînes de caractères larges ; ceux de `_mbsncmp` sont des chaînes de caractères multioctets.  `_mbsncmp` reconnaît les séquences de caractères multioctets selon une page de codes multioctets et retourne `_NLSCMPERROR` en cas d'erreur.  
  
 De plus, `_mbsncmp` et `_mbsncmp_l` vérifient les paramètres.  Si `string1` ou `string2` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, `_mbsncmp` et `_mbsncmp_l` retournent `_NLSCMPERROR` et définissent `errno` à `EINVAL`.  `strncmp` et `wcsncmp` ne vérifient pas leurs paramètres.  Ces fonctions se comportent sinon de façon identique.  
  
 Le comportement de la comparaison de `_mbsncmp` et de `_mbsncmp_l` est affecté par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux.  Ce paramètre contrôle la détection des octets de début et de fin des caractères multioctets.  Pour plus d'informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  La fonction `_mbsncmp` utilise les paramètres régionaux actuels pour ce comportement dépendant des paramètres régionaux.  La fonction `_mbsncmp_l` est identique, sauf qu'elle utilise à la place le paramètre `locale`.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  Si les paramètres régionaux sont des paramètres régionaux sur un seul octet, le comportement de ces fonctions est identique à celui de `strncmp`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnccmp`|`strncmp`|`_mbsncmp`|`wcsncmp`|  
|`_tcsncmp`|`strncmp`|`_mbsnbcmp`|`wcsncmp`|  
|`_tccmp`|Mappe à la macro ou à la fonction inline|`_mbsncmp`|Mappe à la macro ou à la fonction inline|  
|**non applicable**|**non applicable**|`_mbsncmp_l`|**non applicable**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strncmp`|\<string.h\>|  
|`wcsncmp`|\<string.h\> ou \<wchar.h\>|  
|`_mbsncmp`, `_mbsncmp_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strncmp.c  
#include <string.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n      %s\n      %s\n\n",  
           string1, string2 );  
   printf( "Function:   strncmp (first 10 characters only)\n" );  
   result = strncmp( string1, string2 , 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n\n", tmp );  
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );  
   result = _strnicmp( string1, string2, 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n", tmp );  
}  
```  
  
  **Chaînes à comparer :**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown fox jumps over the lazy dog**  
**Fonction :   strncmp \(les 10 premiers caractères uniquement\)**  
**Résultat :      chaîne 1 est supérieure à chaîne 2**  
**Fonction :   strnicmp \_strnicmp \(les 10 premiers caractères uniquement\)**  
**Résultat :      chaîne 1 est égale à chaîne 2**   
## Équivalent .NET Framework  
 [System::String::Compare](frlrfSystemStringClassCompareTopic)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)