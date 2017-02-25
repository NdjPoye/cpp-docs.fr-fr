---
title: "_expand_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_expand_dbg"
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
  - "expand_dbg"
  - "_expand_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "blocs de mémoire, modifier la taille"
  - "expand_dbg, fonction"
  - "_expand_dbg, fonction"
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _expand_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Redimensionne un bloc de mémoire spécifié dans le tas en développant ou en contractant le bloc \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
void *_expand_dbg(   
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Paramètres  
 `userData`  
 Pointeur du bloc de mémoire précédemment allouée.  
  
 `newSize`  
 Nouvelle taille demandée pour le bloc \(en octets\).  
  
 `blockType`  
 Type demandé pour le bloc redimensionné : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Le pointeur du nom du fichier source qui a demandé l'opération de développement ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération de développement a été demandée ou `NULL`.  
  
 Les paramètres `filename` et `linenumber` sont uniquement disponibles si `_expand_dbg` a été appelé explicitement ou si la constante de préprocesseur [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) a été définie.  
  
## Valeur de retour  
 Lors d'une exécution réussie, `_expand_dbg` retourne un pointeur vers le bloc de mémoire redimensionné.  Comme la mémoire n'est pas déplacée, l'adresse est identique à userData.  Si une erreur se produit ou si le bloc n'a pas pu être développé à la taille demandée, il retourne `NULL`.  Si une erreur se produit, `errno` fournit les informations du système d'exploitation sur la nature de l'échec.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_expand_dbg` est une version Debug de la fonction \_[expand](../../c-runtime-library/reference/expand.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_expand_dbg` est réduit à un appel à `_expand`.  `_expand` et `_expand_dbg` redimensionnent un bloc de mémoire dans le tas de base, mais `_expand_dbg` s'adapte à plusieurs fonctionnalités de débogage : mémoires tampons de chaque côté de la partie utilisateur du bloc à déterminer des fuites, un paramètre de type de bloc pour suivre des types spécifiques d'allocation, et `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_expand_dbg` redimensionne le bloc de mémoire spécifié avec légèrement plus d'espace que demandait `newSize`.  `newSize` peut être supérieure ou inférieure à la taille du bloc de mémoire initialement alloué.  L'espace supplémentaire est utilisé par le gestionnaire du tas de débogage pour lier les blocs de mémoire de débogage, pour fournir à l'application les informations d'en\-tête du débogage et pour remplacer des mémoires tampons.  Le redimensionnement est accompli en développant ou en contractant le bloc de mémoire d'origine.  `_expand_dbg` ne déplace pas le bloc de mémoire comme le fait la fonction [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md).  
  
 Lorsque `newSize` est supérieure à la taille des blocs d'origine, le bloc de mémoire est développé.  Pendant une expansion, si le bloc de mémoire ne peut pas être développé pour s'adapter à la taille demandée, `NULL` est retourné.  Lorsque `newSize` est inférieure à la taille des blocs d'origine, le bloc de mémoire est contracté jusqu'à ce que la nouvelle taille soit obtenue.  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour obtenir des informations sur les différences entre appeler une fonction standard du tas et sa version Debug dans une version debug d'une application, consultez [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
 Cette fonction valide ses paramètres.  Si `memblock` est un pointeur null, ou si la taille est supérieure à `_HEAP_MAXREQ`, cette fonction appelle un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à `EINVAL` et la fonction retourne `NULL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_expand_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_expand_dbg.c  
//  
// This program allocates a block of memory using _malloc_dbg  
// and then calls _msize_dbg to display the size of that block.  
// Next, it uses _expand_dbg to expand the amount of  
// memory used by the buffer and then calls _msize_dbg again to  
// display the new amount of memory allocated to the buffer.  
//  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   long *buffer;  
   size_t size;  
  
   // Call _malloc_dbg to include the filename and line number  
   // of our allocation request in the header  
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if( buffer == NULL )  
      exit( 1 );  
  
   // Get the size of the buffer by calling _msize_dbg  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );  
  
   // Expand the buffer using _expand_dbg and show the new size  
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
   if( buffer == NULL )  
      exit( 1 );  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",  
           size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
  **La taille du bloc après le \_malloc\_dbg de 40 longs : 160**  
**Taille de bloc après \_expand\_dbg de 1 plus long : 164**   
## Commentaire  
 La sortie de ce programme dépend de la capacité de votre ordinateur à développer toutes les sections.  Si toutes les sections sont développées, la sortie est renvoyée dans la section de sortie.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)