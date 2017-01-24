---
title: "_msize_dbg | Microsoft Docs"
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
  - "_msize_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_msize_dbg"
  - "msize_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "blocs de mémoire"
  - "_msize_dbg (fonction)"
  - "msize_dbg (fonction)"
ms.assetid: a333f4b6-f8a2-4e61-bb69-cb34063b8cef
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _msize_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la taille d'un bloc de mémoire dans la pile \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
  
      size_t _msize_dbg(  
   void *userData,  
   int blockType   
);  
```  
  
#### Paramètres  
 `userData`  
 Pointeur au bloc mémoire pour lequel il faut déterminer la taille.  
  
 *Type de bloc*  
 Type du bloc de mémoire spécifié : `_CLIENT_BLOCK` ou **\_NORMAL\_BLOCK**.  
  
## Valeur de retour  
 Dans l'achèvement réussi, `_msize_dbg` renvoie la taille \(en octets\) du bloc mémoire spécifié ; sinon il renvoie NULL.  
  
## Notes  
 `_msize_dbg` est une version Debug de la fonction \_[msize](../../c-runtime-library/reference/msize.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_msize_dbg` est réduit à un appel à `_msize`.  A la fois `_msize` et `_msize_dbg` calculent la taille d'un bloc de mémoire dans la pile de base, mais `_msize_dbg` ajoute deux fonctionnalités de débogage : Cela inclut les mémoires tampons de chaque côté de la partie utilisateur du bloc de mémoire dans la taille retournée et permet des calculs de taille pour des types spécifiques de bloc.  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour obtenir des informations sur les différences entre appeler une fonction standard du tas et sa version Debug dans une version debug d'une application, consultez [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
 Cette fonction valide son paramètre.  Si `memblock` est un pointeur null `_msize`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'erreur est gérée, cette fonction affecte `errno` à `EINVAL` et retourne \-1.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_msize_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_msize_dbg.c  
// compile with: /MTd  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then calls _msize_dbg to display the size of that block.  
 * Next, it uses _realloc_dbg to expand the amount of  
 * memory used by the buffer and then calls _msize_dbg again to  
 * display the new amount of memory allocated to the buffer.  
 */  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *buffer, *newbuffer;  
        size_t size;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header  
         */  
        buffer = (long *)_malloc_dbg( 40 * sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        if( buffer == NULL )  
               exit( 1 );  
  
        /*   
         * Get the size of the buffer by calling _msize_dbg  
         */  
        size = _msize_dbg( buffer, _NORMAL_BLOCK );  
        printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );  
  
        /*   
         * Reallocate the buffer using _realloc_dbg and show the new size  
         */  
        newbuffer = _realloc_dbg( buffer, size + (40 * sizeof(long)), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        if( newbuffer == NULL )  
               exit( 1 );  
        buffer = newbuffer;  
        size = _msize_dbg( buffer, _NORMAL_BLOCK );  
        printf( "Size of block after _realloc_dbg of 40 more longs: %u\n", size );  
  
        free( buffer );  
        exit( 0 );  
}  
```  
  
## Sortie  
  
```  
Size of block after _malloc_dbg of 40 longs: 160  
Size of block after _realloc_dbg of 40 more longs: 320  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)