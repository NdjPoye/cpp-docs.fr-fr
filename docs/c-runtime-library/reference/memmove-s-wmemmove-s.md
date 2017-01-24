---
title: "memmove_s, wmemmove_s | Microsoft Docs"
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
  - "wmemmove_s"
  - "memmove_s"
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
  - "wmemmove_s"
  - "memmove_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memmove_s (fonction)"
  - "wmemmove_s (fonction)"
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memmove_s, wmemmove_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace un tampon vers un autre.  Il s'agit de versions de [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
  
      errno_t memmove_s(  
   void *dest,  
   size_t numberOfElements,  
   const void *src,  
   size_t count  
);  
errno_t wmemmove_s(  
   wchar_t *dest,  
   size_t numberOfElements,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### Paramètres  
 `dest`  
 Objet de destination.  
  
 `numberOfElements`  
 Taille de la mémoire tampon de destination.  
  
 `src`  
 Objet source  
  
 `count`  
 Nombre d'octets \(`memmove_s`\) ou de caractères \(`wmemmove_s`\) à copier.  
  
## Valeur de retour  
 Zéro si l'opération a réussi, code d'erreur en cas d'échec.  
  
### Conditions d'erreur  
  
|`dest`|`numberOfElements`|`src`|Valeur de retour|Contenu de `dest`.|  
|------------|------------------------|-----------|----------------------|------------------------|  
|`NULL`|any|any|`EINVAL`|non modifié|  
|any|any|`NULL`|`EINVAL`|non modifié|  
|any|\< `count`|any|`ERANGE`|non modifié|  
  
## Notes  
 Copie des octets `count` de caractères depuis `src` vers `dest`*.* Si certaines zones de la zone de source et de destination se chevauchent, `memmove_s` garantit que les octets de source d'origine dans la région de chevauchement sont copiés avant d'être remplacés.  
  
 Si `dest` ou si `src` est un pointeur null ou si la chaîne de destination est trop petite, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EINVAL` et définissent `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`memmove_s`|\<string.h\>|  
|`wmemmove_s`|\<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_memmove_s.c  
//  
// The program demonstrates the   
// memmove_s function which works as expected  
// for moving overlapping regions.  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   char str[] = "0123456789";  
  
   printf("Before: %s\n", str);  
  
   // Move six bytes from the start of the string  
   // to a new position shifted by one byte. To protect against  
   // buffer overrun, the secure version of memmove requires the  
   // the length of the destination string to be specified.   
  
   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);   
  
   printf_s(" After: %s\n", str);  
}  
```  
  
## Sortie  
  
```  
Before: 0123456789  
 After: 0012345789  
```  
  
## Équivalent .NET Framework  
 [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
## Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)