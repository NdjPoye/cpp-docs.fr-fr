---
title: "_strdup, _wcsdup, _mbsdup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdup"
  - "_mbsdup"
  - "_wcsdup"
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
  - "_tcsdup"
  - "mbsdup"
  - "_mbsdup"
  - "_strdup"
  - "_ftcsdup"
  - "_wcsdup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wcsdup (fonction)"
  - "ftcsdup (fonction)"
  - "_ftcsdup (fonction)"
  - "mbsdup (fonction)"
  - "strdup (fonction)"
  - "_strdup (fonction)"
  - "_wcsdup (fonction)"
  - "copier des chaînes"
  - "dupliquer des chaînes"
  - "chaînes (C++), copie"
  - "_mbsdup (fonction)"
  - "chaînes (C++), de duplication"
  - "tcsdup (fonction)"
  - "_tcsdup (fonction)"
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strdup, _wcsdup, _mbsdup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Duplique les chaînes.  
  
> [!IMPORTANT]
>  `_mbsdup` ne peut pas être utilisée dans les applications qui s’exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *_strdup(  
   const char *strSource   
);  
wchar_t *_wcsdup(  
   const wchar_t *strSource   
);  
unsigned char *_mbsdup(  
   const unsigned char *strSource   
);  
```  
  
#### Paramètres  
 `strSource`  
 Chaîne source se terminant par null.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers l’emplacement de stockage de la chaîne copiée ou `NULL` si le stockage ne peut pas être alloué.  
  
## Notes  
 La fonction `_strdup` appelle [malloc](../../c-runtime-library/reference/malloc.md) pour allouer de l’espace de stockage à une copie de `strSource` et copie ensuite `strSource` dans l’espace alloué.  
  
 `_wcsdup` et `_mbsdup` sont des versions à caractères larges et à caractères multioctets de `_strdup`. Les arguments et la valeur de retour de `_wcsdup` sont des chaînes de caractères larges ; ceux de `_mbsdup` sont des chaînes de caractères multioctets. Ces trois fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 Sachant que `_strdup` appelle `malloc` pour allouer de l’espace de stockage à la copie de `strSource`, il est conseillé de toujours libérer cette mémoire en appelant la routine [free](../../c-runtime-library/reference/free.md) sur le pointeur retourné par l’appel à `_strdup`.  
  
 Si `_DEBUG` et `_CRTDBG_MAP_ALLOC` sont définis, `_strdup` et `_wcsdup` sont remplacés par les appels à `_strdup_dbg` et `_wcsdup_dbg` pour prévoir le débogage des allocations de mémoire. Pour plus d’informations, consultez [\_strdup\_dbg, \_wcsdup\_dbg](../../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strdup`|\<string.h\>|  
|`_wcsdup`|\<string.h\> ou \<wchar.h\>|  
|`_mbsdup`|\<mbstring.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strdup.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is the buffer text";  
   char *newstring;  
   printf( "Original: %s\n", buffer );  
   newstring = _strdup( buffer );  
   printf( "Copy:     %s\n", newstring );  
   free( newstring );  
}  
```  
  
```Output  
Original : il s’agit du texte de la mémoire tampon Copie:     : il s’agit du texte de la mémoire tampon  
```  
  
## Équivalent .NET Framework  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)