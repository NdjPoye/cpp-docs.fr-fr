---
title: "memset, wmemset | Microsoft Docs"
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
  - "wmemset"
  - "memset"
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
  - "memset"
  - "wmemset"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memset (fonction)"
  - "wmemset (fonction)"
ms.assetid: e7ceb01b-df69-49c2-b294-a39358ad4699
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memset, wmemset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Défini la mémoire tampon avec un caractère spécifié.  
  
## Syntaxe  
  
```  
  
      void *memset(  
   void *dest,  
   int c,  
   size_t count   
);  
wchar_t *wmemset(  
   wchar_t *dest,  
   wchar_t c,  
   size_t count  
);  
```  
  
#### Paramètres  
 *dest*  
 Pointeur vers la destination.  
  
 `c`  
 Le caractère à définir.  
  
 *count*  
 Nombre de caractères.  
  
## Valeur de retour  
 Valeur de `dest`.  
  
## Notes  
 Définit les premiers `count` caractères  de`dest` au caractère `c`.  
  
 **Security Note** assurez\-vous que la mémoire tampon de destination a suffisamment d'espace libre pour au moins `count`caractères.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`memset`|\<memory.h\> ou \<string.h\>|  
|`wmemset`|\<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_memset.c  
/* This program uses memset to  
 * set the first four chars of buffer to "*".  
 */  
  
#include <memory.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is a test of the memset function";  
  
   printf( "Before: %s\n", buffer );  
   memset( buffer, '*', 4 );  
   printf( "After:  %s\n", buffer );  
}  
```  
  
## Sortie  
  
```  
Before: This is a test of the memset function  
After:  **** is a test of the memset function  
```  
  
 Voici un exemple de l'utilisation de wmemset :  
  
```  
// crt_wmemset.c  
/* This program uses memset to  
 * set the first four chars of buffer to "*".  
 */  
  
#include <wchar.h>  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buffer[] = L"This is a test of the wmemset function";  
  
   wprintf( L"Before: %s\n", buffer );  
   wmemset( buffer, '*', 4 );  
   wprintf( L"After:  %s\n", buffer );  
}  
```  
  
## Sortie  
  
```  
Before: This is a test of the wmemset function  
After:  **** is a test of the wmemset function  
```  
  
## Équivalent .NET Framework  
 [System::Buffer::SetByte](https://msdn.microsoft.com/en-us/library/system.buffer.setbyte.aspx)  
  
## Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)