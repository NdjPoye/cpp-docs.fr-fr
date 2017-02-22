---
title: "_calloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_calloc_dbg"
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
  - "_calloc_dbg"
  - "calloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_calloc_dbg (fonction)"
  - "calloc_dbg (fonction)"
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _calloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue plusieurs blocs de mémoire dans la pile avec l'espace supplémentaire pour un en\-tête de débogage et les mémoires tampons de remplacement \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Paramètres  
 `num`  
 Nombre demandé de blocs de mémoire.  
  
 `size`  
 Taille demandée de chaque bloc de mémoire \(octets\).  
  
 `blockType`  
 Type de bloc mémoire demandé : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez[Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
 `filename`  
 Le pointeur du nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
 Les paramètres `filename` et `linenumber` sont uniquement disponibles si `_calloc_dbg` a été appelé explicitement ou si la constante de préprocesseur [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) a été définie.  
  
## Valeur de retour  
 Dans l'achèvement réussi, le retour de cette fonction ou un pointeur vers la partie utilisateur du bloc de mémoire réaffecté en dernier, appelle la nouvelle fonction gestionnaire, ou renvoie `NULL`.  Pour une description complète du comportement de retour, consultez la section Remarques.  Pour plus d'informations sur la façon dont la nouvelle fonction gestionnaire est utilisée, consultez la fonction [calloc](../../c-runtime-library/reference/calloc.md).  
  
## Notes  
 `_calloc_dbg` est une version Debug de la fonction [calloc](../../c-runtime-library/reference/calloc.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_calloc_dbg` est réduit à un appel à `calloc`.  A la fois `calloc` et `_calloc_dbg` allouent des blocs mémoire de `num` dans la pile de base, mais `_calloc_dbg` propose plusieurs fonctionnalités de débogage:  
  
-   Mémoires tampons de chaque côté de la partie utilisateur du bloc à déterminer les fuites.  
  
-   Un paramètre de type bloc pour suivre les types spécifiques d'allocation.  
  
-   informations de `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_calloc_dbg` alloue chaque bloc mémoire avec légèrement plus d'espace que le `size`demandé.  L'espace supplémentaire est utilisé par le gestionnaire du tas de débogage pour lier les blocs de mémoire de débogage, pour fournir à l'application les informations d'en\-tête du débogage et pour remplacer des mémoires tampons.  Lorsque le bloc est alloué, la partie utilisateur du bloc est remplie avec la valeur 0xCD et chacune des mémoires tampons de remplacement est remplie avec 0xFD.  
  
 `_calloc_dbg` définit `errno` à `ENOMEM` si une allocation de mémoire échoue; `EINVAL` est renvoyé si la quantité de mémoire nécessaire \(charge mémoire y compris mentionnée précédemment\) dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour obtenir des informations sur les différences entre appeler une fonction standard en pile contre sa version Debug dans une version debug d'une application, consultez [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_calloc_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
  **Mémoire allouée avec succès**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [\_DEBUG](../../c-runtime-library/debug.md)