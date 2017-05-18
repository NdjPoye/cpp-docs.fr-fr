---
title: _freea | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _freea
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
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 18
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: bd53960a97cc6647008b683e354df664941428e9
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="freea"></a>_freea
Libère un bloc de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Bloc mémoire précédemment alloué à libérer.  
  
## <a name="return-value"></a>Valeur de retour  
 Aucun  
  
## <a name="remarks"></a>Notes  
 La fonction `_freea` libère un bloc de mémoire (`memblock`) alloué par un appel à [_malloca](../../c-runtime-library/reference/malloca.md). `_freea` vérifie si la mémoire a été allouée sur le tas ou la pile. Si elle a été allouée sur la pile, `_freea` n’exécute aucune opération. Si elle a été allouée sur le tas, le nombre d’octets libérés est équivalent au nombre d’octets demandés quand le bloc a été alloué. Si `memblock` a la valeur `NULL`, le pointeur est ignoré et `_freea` retourne le contrôle immédiatement. Tenter de libérer un pointeur non valide (un pointeur désignant un bloc de mémoire qui n’était pas alloué par `_malloca`) peut affecter les demandes d’allocation ultérieures et provoquer des erreurs.  
  
 `_freea`appels `free` en interne si elle détecte que la mémoire est allouée sur le tas. Un marqueur placé en mémoire à l’adresse qui précède immédiatement la mémoire allouée détermine si celle-ci est sur le tas ou la pile.  
  
 Si une erreur se produit pendant la libération de la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de la défaillance. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Une fois qu’un bloc de mémoire a été libéré, [_heapmin](../../c-runtime-library/reference/heapmin.md) réduit la quantité de mémoire disponible sur le tas en fusionnant les régions inutilisées et en les libérant pour le système d’exploitation. La mémoire libérée qui n’est pas mise à la disposition du système d’exploitation est restaurée vers le pool libre et peut être réallouée.  
  
 Un appel à `_freea` doit accompagner tous les appels à `_malloca`. En outre, appeler `_freea` deux fois sur la même mémoire constitue une erreur. Quand l’application est liée à une version de débogage des bibliothèques Runtime C, en particulier si les fonctionnalités [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) sont activées en définissant `_CRTDBG_MAP_ALLOC`, il est plus facile de rechercher des appels manquants ou dupliqués à `_freea`. Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 `_freea` est marqué `__declspec(noalias)`, ce qui signifie que la fonction ne peut pas modifier les variables globales. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_freea`|\<stdlib.h> et \<malloc.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)
