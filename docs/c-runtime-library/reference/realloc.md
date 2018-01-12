---
title: realloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: realloc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs: C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 525b0f0877471b5bfd6d9fa16551b21908f229a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="realloc"></a>realloc
Réallouent les blocs de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Pointeur désignant le bloc de mémoire précédemment alloué.  
  
 `size`  
 Nouvelle taille en octets.  
  
## <a name="return-value"></a>Valeur de retour  
 `realloc` retourne un pointeur `void` vers le bloc de mémoire réalloué (et éventuellement déplacé).  
  
 Si la quantité de mémoire disponible ne suffit pas à agrandir le bloc à la taille donnée, le bloc d’origine reste inchangé, et `NULL` est retourné.  
  
 Si `size` a la valeur zéro, le bloc désigné par `memblock` est libéré ; la valeur de retour est `NULL`, et `memblock` pointe vers un bloc libéré.  
  
 La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet. Pour obtenir un pointeur vers un autre type que `void`, utilisez un cast de type sur la valeur de retour.  
  
## <a name="remarks"></a>Notes  
 La fonction `realloc` modifie la taille d’un bloc de mémoire alloué. L’argument `memblock` pointe vers le début du bloc de mémoire. Si `memblock` a la valeur `NULL`, `realloc` se comporte de la même façon que `malloc` et alloue un nouveau bloc de `size` octets. Si `memblock` n’a pas la valeur `NULL`, il doit correspondre à un pointeur retourné par un appel précédent à `calloc`, `malloc` ou `realloc`.  
  
 L’argument `size` indique la nouvelle taille du bloc, en octets. Le contenu du bloc est inchangé tant que la plus courte des tailles nouvelle et ancienne n’est pas atteinte, même si le nouveau bloc peut se trouver à un autre emplacement. Sachant que le nouveau bloc peut se trouver à un nouvel emplacement de mémoire, il n’est pas garanti que le pointeur retourné par `realloc` soit le pointeur transmis via l’argument `memblock`. `realloc` ne remet pas à zéro la mémoire nouvellement allouée dans le cas d’une croissance de la mémoire tampon.  
  
 `realloc` affecte à `errno` la valeur `ENOMEM` si l’allocation de mémoire échoue ou si la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`. Pour plus d’informations sur ce code d’erreur et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `realloc` appelle `malloc` pour utiliser la fonction C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) dans le but de définir le mode de nouveau gestionnaire. Le mode de nouveau gestionnaire indique si, en cas d’échec, `malloc` doit appeler la routine de nouveau gestionnaire, telle qu’elle est définie par [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Par défaut, `malloc` n’appelle pas la routine de nouveau gestionnaire en cas d’échec d’allocation de mémoire. Vous pouvez remplacer ce comportement par défaut de sorte que, quand _`realloc` ne parvient pas à allouer de la mémoire, `malloc` appelle la routine de nouveau gestionnaire de la même façon que l’opérateur `new` quand il échoue pour la même raison. Pour remplacer la valeur par défaut, appelez  
  
```  
_set_new_mode(1)  
```  
  
 au début de votre programme, ou créez un lien avec NEWMODE.OBJ (consultez [Options de lien](../../c-runtime-library/link-options.md)).  
  
 Quand l’application est liée à une version de débogage des bibliothèques Runtime C, `realloc` se résout en [_realloc_dbg](../../c-runtime-library/reference/realloc-dbg.md). Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 `realloc` est marqué `__declspec(noalias)` et `__declspec(restrict)`, ce qui signifie que la fonction ne peut pas modifier les variables globales et que le pointeur retourné n’a pas d’alias. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`realloc`|\<stdlib.h> et \<malloc.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
Size of block after malloc of 1000 longs: 4000  
Size of block after realloc of 1000 more longs: 8000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)