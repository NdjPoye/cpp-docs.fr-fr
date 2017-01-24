---
title: "_memccpy | Microsoft Docs"
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
  - "_memccpy"
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
  - "_memccpy"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_memccpy (fonction)"
  - "memccpy (fonction)"
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _memccpy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie les caractères d'une mémoire tampon.  
  
## Syntaxe  
  
```  
  
      void *_memccpy(  
   void *dest,  
   const void *src,  
   int c,  
   size_t count   
);  
```  
  
#### Paramètres  
 *dest*  
 Pointeur vers la destination.  
  
 *src*  
 Pointeur vers la source.  
  
 `c`  
 Dernier caractère à copier.  
  
 *count*  
 Nombre de caractères.  
  
## Valeur de retour  
 Si le caractère `c` est copié, `_memccpy` retourne un pointeur vers une valeur char dans *dest* qui suit immédiatement le caractère.  Si `c` n'est pas copié, il retourne **NULL**.  
  
## Notes  
 La fonction `_memccpy` copie 0 caractères ou plus de caractères de *src* vers *dest*, s'arrête lorsque le caractère `c` a été copié ou lorsque *count* caractères ont été copiés, selon l'événement se produisant en premier.  
  
 **Remarque sur la sécurité :**  Assurez \-vous que la mémoire tampon de destination est la même taille ou supérieure à la mémoire tampon source.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_memccpy`|\<memory.h\> ou \<string.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_memccpy.c  
  
#include <memory.h>  
#include <stdio.h>  
#include <string.h>  
  
char string1[60] = "The quick brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char buffer[61];  
   char *pdest;  
  
   printf( "Function: _memccpy 60 characters or to character 's'\n" );  
   printf( "Source: %s\n", string1 );  
   pdest = _memccpy( buffer, string1, 's', 60 );  
   *pdest = '\0';  
   printf( "Result: %s\n", buffer );  
   printf( "Length: %d characters\n", strlen( buffer ) );  
}  
```  
  
## Sortie  
  
```  
Function: _memccpy 60 characters or to character 's'  
Source: The quick brown dog jumps over the lazy fox  
Result: The quick brown dog jumps  
Length: 25 characters  
```  
  
## Équivalent .NET Framework  
  
-   [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
-   [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)