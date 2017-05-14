---
title: _msize_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _msize_dbg
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
apitype: DLLExport
f1_keywords:
- _msize_dbg
- msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- _msize_dbg function
- msize_dbg function
ms.assetid: a333f4b6-f8a2-4e61-bb69-cb34063b8cef
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6e26ab437a5fceb148e0c49308b244ae0a39504e
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="msizedbg"></a>_msize_dbg
Calcule la taille d’un bloc de mémoire dans le tas (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      size_t _msize_dbg(  
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `userData`  
 Pointeur désignant le bloc de mémoire duquel déterminer la taille.  
  
 *blockType*  
 Type du bloc de mémoire spécifié : `_CLIENT_BLOCK` ou **_NORMAL_BLOCK**.  
  
## <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, `_msize_dbg` retourne la taille (en octets) du bloc de mémoire spécifié ; sinon, elle retourne la valeur NULL.  
  
## <a name="remarks"></a>Notes  
 `_msize_dbg` est une version de débogage de la fonction _[msize](../../c-runtime-library/reference/msize.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_msize_dbg` est réduit à un appel à `_msize`. `_msize` et `_msize_dbg` calculent toutes deux la taille d’un bloc de mémoire dans le tas de base, mais `_msize_dbg` ajoute deux fonctionnalités de débogage : elle inclut les mémoires tampons de chaque côté de la partie utilisateur du bloc de mémoire dans la taille retournée et elle permet de calculer la taille de types de blocs spécifiques.  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans une build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
 Cette fonction valide son paramètre. Si `memblock` est un pointeur Null, `_msize` appelle un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’erreur est gérée, la fonction définit `errno` sur `EINVAL` et retourne -1.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_msize_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="output"></a>Sortie  
  
```  
Size of block after _malloc_dbg of 40 longs: 160  
Size of block after _realloc_dbg of 40 more longs: 320  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)
