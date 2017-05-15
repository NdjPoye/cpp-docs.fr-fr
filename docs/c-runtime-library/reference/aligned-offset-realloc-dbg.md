---
title: _aligned_offset_realloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0e3e8a35d2b33417e952155313307aa55f181eb4
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg
Modifie la taille d’un bloc de mémoire qui a été alloué avec [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void * _aligned_offset_realloc_dbg(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `memblock`  
 Pointeur de bloc de mémoire actif.  
  
 [in] `size`  
 Taille de l'allocation de mémoire.  
  
 [in] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 [in] `offset`  
 Décalage dans l'allocation de mémoire pour forcer l'alignement.  
  
 [in] `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération `aligned_offset_realloc` ou NULL.  
  
 [in] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération `aligned_offset_realloc` a été demandée ou NULL.  
  
## <a name="return-value"></a>Valeur de retour  
 `_aligned_offset_realloc_dbg` retourne un pointeur void vers le bloc de mémoire réalloué (et éventuellement déplacé). La valeur de retour est `NULL` si la taille est égale à zéro et l'argument de mémoire tampon n'est pas `NULL`, ou si la mémoire disponible est insuffisante pour étendre le bloc à la taille donnée. Dans le premier cas, le bloc d'origine est libéré. Dans le second cas, le bloc d'origine est inchangé. La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet. Pour obtenir un pointeur vers un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
## <a name="remarks"></a>Notes  
 `_aligned_offset_realloc_dbg` est une version de débogage de la fonction [_aligned_offset_realloc](../../c-runtime-library/reference/aligned-offset-realloc.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_aligned_offset_realloc_dbg` est réduit à un appel à `_aligned_offset_realloc`. `_aligned_offset_realloc` et `_aligned_offset_realloc_dbg` réallouent toutes deux un bloc de mémoire dans le tas de base, mais `_aligned_offset_realloc_dbg` gère plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d’allocation spécifiques et des informations `filename`/`linenumber` pour déterminer l’origine des demandes d’allocation.  
  
 Comme [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_realloc_dbg` autorise une structure à être alignée au niveau d’un décalage au sein de la structure.  
  
 `_realloc_dbg` réalloue le bloc de mémoire spécifié avec un peu plus d'espace que la valeur `newSize` demandée. `newSize` peut être inférieure ou supérieure à la taille du bloc de mémoire alloué initialement. L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en-têtes de débogage et les mémoires tampons de remplacement. La réallocation peut entraîner un déplacement du bloc de mémoire initial vers un emplacement différent dans le tas, ainsi qu'une modification de la taille du bloc de mémoire. Si le bloc de mémoire est déplacé, son contenu d'origine est remplacé.  
  
 Cette fonction affecte à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée était supérieure à `_HEAP_MAXREQ`. Pour plus d’informations sur `errno`, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). De plus, `_aligned_offset_realloc_dbg` valide ses paramètres. Si `alignment` n’est pas une puissance de 2 ou si `offset` est supérieur ou égal à `size` et différent de zéro, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte la valeur `errno` à `EINVAL`.  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_realloc_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
