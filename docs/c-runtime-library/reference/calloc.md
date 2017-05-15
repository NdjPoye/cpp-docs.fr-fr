---
title: calloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- calloc
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
- calloc
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
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
ms.openlocfilehash: a8b0fab02487291625d67706675c62e9a737718f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="calloc"></a>calloc
Alloue un tableau dans la mémoire avec des éléments initialisés à 0.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `num`  
 Nombre d'éléments.  
  
 `size`  
 Longueur en octets de chaque élément.  
  
## <a name="return-value"></a>Valeur de retour  
 `calloc` retourne un pointeur désignant l’espace alloué. L’espace de stockage désigné par la valeur de retour est obligatoirement aligné correctement pour le stockage de tout type d’objet. Pour obtenir un pointeur désignant un type autre que `void`, utilisez un cast de type sur la valeur de retour.  
  
## <a name="remarks"></a>Notes  
 La fonction `calloc` alloue de l’espace de stockage pour un tableau de `num` éléments occupant chacun `size` octets. Chaque élément est initialisé à 0.  
  
 `calloc` définit `errno` sur `ENOMEM` si une allocation de mémoire échoue ou que la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`. Pour plus d’informations sur ce code d’erreur et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `calloc` appelle `malloc` pour utiliser la fonction C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) afin de définir le nouveau mode de gestionnaire. Le nouveau mode de gestionnaire indique si, en cas d’échec, `malloc` doit appeler la nouvelle routine de gestionnaire, telle qu’elle est définie par [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Par défaut, `malloc` n’appelle pas la routine de nouveau gestionnaire en cas d’échec d’allocation de mémoire. Vous pouvez remplacer ce comportement par défaut de sorte que, quand _`calloc` ne parvient pas à allouer de la mémoire, `malloc` appelle la routine de nouveau gestionnaire de la même façon que l’opérateur `new` quand il échoue pour la même raison. Pour ce faire, appelez  
  
```  
_set_new_mode(1)  
```  
  
 au début de votre programme, ou créez un lien avec NEWMODE.OBJ (consultez [Options de lien](../../c-runtime-library/link-options.md)).  
  
 Quand l’application est liée à une version de débogage des bibliothèques Runtime C, `calloc` se résout en [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md). Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 `calloc` est marqué `__declspec(noalias)` et `__declspec(restrict)`, ce qui signifie que la fonction ne peut pas modifier les variables globales et que le pointeur retourné n’a pas d’alias. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`calloc`|\<stdlib.h> et \<malloc.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
```Output  
Allocated 40 long integers  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
