---
title: "memcpy_s, wmemcpy_s | Microsoft Docs"
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
  - "memcpy_s"
  - "wmemcpy_s"
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
  - "wmemcpy_s"
  - "memcpy_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memcpy_s (fonction)"
  - "wmemcpy_s (fonction)"
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memcpy_s, wmemcpy_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie des octets entre les mémoires tampon. Voici les versions de [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### Paramètres  
 `dest`  
 Nouvelle mémoire tampon.  
  
 `destSize`  
 Taille de la mémoire tampon de destination, en octets, des caractères larges \(wchar\_t\) pour wmemcpy\_s memcpy\_s.  
  
 `src`  
 Mémoire tampon à partir de laquelle effectuer la copie.  
  
 `count`  
 Nombre de caractères à copier.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
### Conditions d’erreur  
  
|`dest`|`destSize`|`src`|Valeur de retour|Contenu de `dest`|  
|------------|----------------|-----------|----------------------|-----------------------|  
|`NULL`|any|any|`EINVAL`|non modifié|  
|any|any|`NULL`|`EINVAL`|`dest` est remis à zéro|  
|any|\< `count`|any|`ERANGE`|`dest` est remis à zéro|  
  
## Notes  
 `memcpy_s` copie `count` octets de `src` vers `dest` ; `wmemcpy_s` copie `count` caractères larges \(sur deux octets\). Si la source et la destination se chevauchent, le comportement de `memcpy_s` n'est pas défini. Utilisez `memmove_s` pour gérer les régions qui se chevauchent.  
  
 Ces fonctions valident leurs paramètres. Si `dest` ou `src` est un pointeur null, ou `destSize` est inférieure à `count`, ces fonctions appellent le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EINVAL` et définissent `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`memcpy_s`|\<memory.h\> ou \<string.h\>|  
|`wmemcpy_s`|\<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)