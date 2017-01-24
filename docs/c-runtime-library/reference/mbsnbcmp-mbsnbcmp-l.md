---
title: "_mbsnbcmp, _mbsnbcmp_l | Microsoft Docs"
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
  - "_mbsnbcmp"
  - "_mbsnbcmp_l"
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
  - "mbsnbcmp"
  - "tcsnbmp"
  - "_mbsnbcmp_l"
  - "mbsnbcmp_l"
  - "_mbsnbcmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcmp (fonction)"
  - "_mbsnbcmp_l (fonction)"
  - "_tcsncmp (fonction)"
  - "mbsnbcmp (fonction)"
  - "mbsnbcmp_l (fonction)"
  - "tcsncmp (fonction)"
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbcmp, _mbsnbcmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare les `n` premiers octets de deux chaînes de caractères multioctets.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcmp_l(  
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
 La valeur de retour indique la relation ordinale entre les sous\-chaînes de `string1` et de `string`.  
  
|Valeur de retour|Description|  
|----------------------|-----------------|  
|\< 0|La sous\-chaîne de `string1` est inférieure à la sous\-chaîne de `string2`.|  
|0|La sous\-chaîne de `string1` est identique à la sous\-chaîne de `string2`.|  
|\> 0|La sous\-chaîne de `string1` est supérieure à la sous\-chaîne de `string2`.|  
  
 En cas d'erreur de validation d'un paramètre, `_mbsnbcmp` et `_mbsnbcmp_l` retournent `_NLSCMPERROR`, qui est défini dans \<string.h\> et dans \<mbstring.h\>.  
  
## Notes  
 Les fonctions `_mbsnbcmp` comparent au plus les `count` premiers octets de `string1` et de `string2`, et retournent une valeur qui indique la relation entre les sous\-chaînes.  `_mbsnbcmp` est une version respectant la casse de `_mbsnbicmp`.  Contrairement à `_mbsnbcoll`, `_mbsnbcmp` n'est pas affectée par l'ordre de classement des paramètres régionaux.  `_mbsnbcmp` reconnaît les séquences de caractères multioctets en fonction de la [page de codes](../../c-runtime-library/code-pages.md) multioctet active.  
  
 `_mbsnbcmp` ressemble à `_mbsncmp`, sauf que `_mbsncmp` compare des chaînes de caractères et non pas des octets.  
  
 La valeur de sortie est affectée par le paramètre de catégorie `LC_CTYPE` des paramètres régionaux, qui spécifie les octets de début et de fin des caractères multioctets.  Pour plus d'informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  La fonction `_mbsnbcmp` utilise les paramètres régionaux actuels pour ce comportement dépendant des paramètres régionaux.  La fonction `_mbsnbcmp_l` est identique, sauf qu'elle utilise à la place le paramètre `locale`.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `string1` ou `string2` est un pointeur null, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, les fonctions retournent `_NLSCMPERROR` et `errno` est défini à `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsncmp`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcmp`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
|`_tcsncmp_l`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcml`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnbcmp`|\<mbstring.h\>|  
|`_mbsnbcmp_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_mbsnbcmp.c  
#include <mbstring.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n          %s\n", string1 );  
   printf( "          %s\n\n", string2 );  
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );  
   result = _mbsncmp( string1, string2 , 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );  
   result = _mbsnicmp( string1, string2, 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
}  
```  
  
## Sortie  
  
```  
Compare strings:  
          The quick brown dog jumps over the lazy fox  
          The QUICK brown fox jumps over the lazy dog  
  
Function: _mbsnbcmp (first 10 characters only)  
Result:   String 1 is greater than string 2  
  
Function: _mbsnicmp _mbsnicmp (first 10 characters only)  
Result:   String 1 is equal to string 2  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)