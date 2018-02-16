---
title: free | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- free
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
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 161b067c432a30e58db51410f0540d60d5e74bc8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="free"></a>free
Libère un bloc de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Bloc mémoire précédemment alloué à libérer.  
  
## <a name="remarks"></a>Notes  
 La fonction `free` libère un bloc de mémoire (`memblock`) alloué par un appel à `calloc`, `malloc` ou `realloc`. Le nombre d’octets libérés est équivalent au nombre d’octets demandés quand le bloc a été alloué (ou réalloué, dans le cas de `realloc`). Si `memblock` a la valeur `NULL`, le pointeur est ignoré et `free` retourne le contrôle immédiatement. Tenter de libérer un pointeur non valide (un pointeur désignant un bloc de mémoire qui n’était pas alloué par `calloc`, `malloc` ou `realloc`) peut affecter les demandes d’allocation ultérieures et provoquer des erreurs.  
  
 Si une erreur se produit pendant la libération de la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de la défaillance. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Une fois qu’un bloc de mémoire a été libéré, [_heapmin](../../c-runtime-library/reference/heapmin.md) réduit la quantité de mémoire disponible sur le tas en fusionnant les régions inutilisées et en les libérant pour le système d’exploitation. La mémoire libérée qui n’est pas mise à la disposition du système d’exploitation est restaurée vers le pool libre et peut être réallouée.  
  
 Quand l’application est liée à une version de débogage des bibliothèques Runtime C, `free` se résout en [_free_dbg](../../c-runtime-library/reference/free-dbg.md). Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 `free` est marqué `__declspec(noalias)`, ce qui signifie que la fonction ne peut pas modifier les variables globales. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md).  
  
 Pour libérer de la mémoire allouée avec [_malloca](../../c-runtime-library/reference/malloca.md), utilisez [_freea](../../c-runtime-library/reference/freea.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`free`|\<stdlib.h> et \<malloc.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [malloc](../../c-runtime-library/reference/malloc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)