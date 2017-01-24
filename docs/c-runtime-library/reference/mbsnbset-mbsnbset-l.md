---
title: "_mbsnbset, _mbsnbset_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbset"
  - "_mbsnbset_l"
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
  - "mbsnbset"
  - "mbsnbset_l"
  - "_mbsnbset"
  - "_mbsnbset_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbset (fonction)"
  - "_mbsnbset_l (fonction)"
  - "_tcsnset (fonction)"
  - "_tcsnset_l (fonction)"
  - "mbsnbset (fonction)"
  - "mbsnbset_l (fonction)"
  - "tcsnset (fonction)"
  - "tcsnset_l (fonction)"
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbset, _mbsnbset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the first `n` bytes of a multibyte\-character string to a specified character.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_mbsnbset\_s, \_mbsnbset\_s\_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
unsigned char *_mbsnbset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnbset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `str`  
 Chaîne à modifier.  
  
 `c`  
 Single\-byte or multibyte\-character setting.  
  
 `count`  
 Number of bytes to be set.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_mbsnbset` returns a pointer to the altered string.  
  
## Notes  
 The `_mbsnbset` and `_mbsnbset_l` functions set, at most, the first `count` bytes of `str` to `c`.  If `count` is greater than the length of `str`, the length of `str` is used instead of `count`.  If `c` is a multibyte character and cannot be set entirely into the last byte specified by `count`, the last byte is padded with a blank character.  `_mbsnbset` and `_mbsnbset_l`does not place a terminating null at the end of `str`.  
  
 `_mbsnbset` and `_mbsnbset_l`is similar to `_mbsnset`, except that it sets `count` bytes rather than `count` characters of `c`.  
  
 If `str` is `NULL` or `count` is zero, this function generates an invalid parameter exception as described in [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  If execution is allowed to continue, `errno` is set to `EINVAL` and the function returns `NULL`.  Also, if `c` is not a valid multibyte character, `errno` is set to `EINVAL` and a space is used instead.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  La version `_mbsnbset` de cette fonction utilise les paramètres régionaux actuels pour ce comportement dépendant des paramètres régionaux; la version `_mbsnbset_l` est identique à part qu'elle utilise les paramètres régionaux passés à place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 **Security Note** This API incurs a potential threat brought about by a buffer overrun problem.  Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnbset`|\<mbstring.h\>|  
|`_mbsnbset_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_mbsnbset.c  
// compile with: /W3  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset( string, '*', 4 ); // C4996  
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
## Sortie  
  
```  
Before: This is a test  
After:  **** is a test  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)