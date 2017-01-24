---
title: "_memicmp, _memicmp_l | Microsoft Docs"
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
  - "_memicmp_l"
  - "_memicmp"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_memicmp"
  - "memicmp_l"
  - "_memicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_memicmp (fonction)"
  - "_memicmp_l (fonction)"
  - "memicmp (fonction)"
  - "memicmp_l (fonction)"
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _memicmp, _memicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare les caractères dans les deux mémoires tampons \(respectent pas la casse\).  
  
## Syntaxe  
  
```  
int _memicmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count   
);  
int _memicmp_l(  
   const void *buf1,  
   const void *buf2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `buf1`  
 Première mémoire tampon.  
  
 `buf2`  
 Deuxième mémoire tampon.  
  
 `count`  
 Nombre de caractères.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 La valeur de retour indique la relation entre les mémoires tampons.  
  
|Valeur de retour|Relation des premiers octets de nombre de buf1 et de buf2|  
|----------------------|---------------------------------------------------------------|  
|\< 0|`buf1` inférieure à `buf2`|  
|0|`buf1` identique à `buf2`|  
|\> 0|`buf1` est supérieur à `buf2`.|  
|`_NLSCMPERROR`|Une erreur s'est produite.|  
  
## Notes  
 La fonction `_memicmp` compare les premiers caractères de `count` les deux mémoires tampons `buf1` et l'`buf2` octet par octet.  La comparaison ne respecte pas la casse.  
  
 Si `buf1` ou `buf2` est un pointeur null, cette fonction invoque un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne `_NLSCMPERROR` et définit `errno` à la valeur `EINVAL`.  
  
 `_memicmp` utilise les paramètres régionaux actuels pour tout comportement dépend des paramètres régionaux ; `_memicmp_l` est identique à la différence qu'il utilise les paramètres régionaux transmis à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_memicmp`|\<memory.h\> ou \<string.h\>|  
|`_memicmp_l`|\<memory.h\> ou \<string.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_memicmp.c  
// This program uses _memicmp to compare  
// the first 29 letters of the strings named first and  
// second without regard to the case of the letters.  
  
#include <memory.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   int result;  
   char first[] = "Those Who Will Not Learn from History";  
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";  
   // Note that the 29th character is right here ^  
  
   printf( "Compare '%.29s' to '%.29s'\n", first, second );  
   result = _memicmp( first, second, 29 );  
   if( result < 0 )  
      printf( "First is less than second.\n" );  
   else if( result == 0 )  
      printf( "First is equal to second.\n" );  
   else if( result > 0 )  
      printf( "First is greater than second.\n" );  
}  
```  
  
  **Comparez « Ceux Qui N'Apprendront Pas » les « CEUX QUI N'APPRENDRONT PAS »**  
**Est d'abord égal au second.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)