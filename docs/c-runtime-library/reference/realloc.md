---
title: "realloc | Microsoft Docs"
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
  - "realloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_brealloc"
  - "_nrealloc"
  - "realloc"
  - "_frealloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_brealloc (fonction)"
  - "realloc (fonction)"
  - "nrealloc (fonction)"
  - "frealloc (fonction)"
  - "_nrealloc (fonction)"
  - "blocs de mémoire, réallouer"
  - "mémoire, réallouer"
  - "_frealloc (fonction)"
  - "réallouer des blocs de mémoire"
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Réalloue des blocs de mémoire.  
  
## Syntaxe  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### Paramètres  
 `memblock`  
 Pointeur vers un bloc de mémoire précédemment allouée.  
  
 `size`  
 Nouvelle taille en octets.  
  
## Valeur de retour  
 `realloc` retourne un pointeur `void` sur le bloc mémoire realloué \(et éventuellement déplacé\).  
  
 S'il n'y a pas assez de mémoire pour développer le bloc à la taille spécifiée, le bloc d'origine reste inchangé, et `NULL` est retourné.  
  
 Si `size` est zéro, le bloc référencé par `memblock` est récupéré ; la valeur de retour est `NULL`, et `memblock` est laissé, le curseur vers un bloc libéré.  
  
 Les valeur de retour pointent vers un espace de stockage, qui est garanti d'etre aligné correctement pour le stockage de n'importe quel types d'objet.  Pour obtenir un pointeur sur un type autre qu'un `void`, utilisez un cast de type sur la valeur de retour.  
  
## Notes  
 La fonction `realloc` change la taille d'un bloc de mémoire allouée.  L'argument `memblock` pointe au début du bloc de mémoire.  Si `memblock` est `NULL`, `realloc` se comporte de la même manière que `malloc` et alloue un nouveau bloc d'octets de dimension `size`.  Si `memblock` n'est pas `NULL`, ce doit être un pointeur retourné par un appel précédent à `calloc`,`malloc`, ou à `realloc`.  
  
 L'argument `size` présente la nouvelle taille du bloc, en octets.  Le contenu du bloc reste inchangé jusqu'à la plus petite de la nouvelle et de l'ancienne taille, bien que le nouveau bloc peut se trouver dans un emplacement différent.  Étant donné que le nouveau bloc peut se trouver dans un emplacement de mémoire, le pointeur retourné par `realloc` n'est pas garanti être un pointeur passé via l'argument `memblock`.  `realloc` ne met pas la mémoire récemment allouée à zéro dans le cas de l'augmentation de la mémoire tampon.  
  
 `realloc` affecte à `errno` la valeur `ENOMEM` si l'allocation de mémoire échoue ou si la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ceci et sur les codes d'erreurs, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `realloc`  appelle `malloc` pour utiliser la fonction C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) pour définir le nouveau mode gestionnaire.  Le nouveau mode de gestionnaire indique si, en cas de échec, `malloc` doit appeler la nouvelle routine du gestionnaire comme définit par [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  Par défaut, `malloc` n'appelle pas la nouvelle routine de gestionnaire en cas de défaillance pour allouer de la mémoire.  Vous pouvez substituer ce comportement par défaut afin que, lorsque `realloc` ne réussit pas à allouer la mémoire, `malloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur `new` lorsqu'il échoue pour la même raison.  Pour substituer la valeur par défaut, appelez  
  
```  
_set_new_mode(1)  
```  
  
 tôt dans vos programmes, ou créez un lien avec NEWMODE.OBJ \(consultez [Options de lien](../../c-runtime-library/link-options.md)\).  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `realloc` est résolu en [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `realloc` est marqué `__declspec(noalias)` et `__declspec(restrict)` ; cela signifie que la fonction ne modifiera pas de variables globales et que le pointeur retourné n'est pas sous la forme d'un alias.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`realloc`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_realloc.c  
// This program allocates a block of memory for  
// buffer and then uses _msize to display the size of that  
// block. Next, it uses realloc to expand the amount of  
// memory used by buffer and then calls _msize again to  
// display the new amount of memory allocated to buffer.  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   long *buffer, *oldbuffer;  
   size_t size;  
  
   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )  
      exit( 1 );  
  
   size = _msize( buffer );  
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );  
  
   // Reallocate and show new size:  
   oldbuffer = buffer;     // save pointer in case realloc fails  
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))   
        ==  NULL )  
   {  
      free( oldbuffer );  // free original block  
      exit( 1 );  
   }  
   size = _msize( buffer );  
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",   
            size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
  **La taille du bloc après le malloc de longueur 1000 : 4000**  
**La taille du bloc après le realloc de longueur supplémentaire 1000 : 8000**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)