---
title: _aligned_recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
dev_langs: C++
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f434c09e22933859b227f2517e124e9ca668e2cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedrecallocdbg"></a>_aligned_recalloc_dbg
Modifie la taille d’un bloc de mémoire qui a été alloué avec [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0 (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void * _aligned_recalloc_dbg(  
   void * memblock,   
   size_t num,  
   size_t size,   
   size_t alignment,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `memblock`  
 Pointeur de bloc de mémoire actif.  
  
 [in] `num`  
 Nombre d'éléments.  
  
 [in] `size`  
 Taille en octets de chaque élément.  
  
 [in] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 [in] `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 [in] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## <a name="return-value"></a>Valeur de retour  
 `_aligned_recalloc_dbg` retourne un pointeur void vers le bloc de mémoire réalloué (et éventuellement déplacé). La valeur de retour est `NULL` si la taille est égale à zéro et l'argument de mémoire tampon n'est pas `NULL`, ou si la mémoire disponible est insuffisante pour étendre le bloc à la taille donnée. Dans le premier cas, le bloc d'origine est libéré. Dans le second cas, le bloc d'origine est inchangé. La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet. Pour obtenir un pointeur vers un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
 Le fait de réallouer la mémoire et de modifier l'alignement d'un bloc constitue une erreur.  
  
## <a name="remarks"></a>Notes  
 `_aligned_recalloc_dbg` est une version de débogage de la fonction [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_aligned_recalloc_dbg` est réduit à un appel à `_aligned_recalloc`. `_aligned_recalloc` et `_aligned_recalloc_dbg` réallouent toutes deux un bloc de mémoire dans le tas de base, mais `_aligned_recalloc_dbg` gère plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d’allocation spécifiques et des informations `filename`/`linenumber` pour déterminer l’origine des demandes d’allocation.  
  
 `_aligned_recalloc_dbg` réalloue le bloc de mémoire spécifié avec un peu plus d’espace que la taille demandée (`num` * `size`), ce qui peut donner une taille inférieure ou supérieure à la taille du bloc de mémoire alloué initialement. L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en-têtes de débogage et les mémoires tampons de remplacement. La réallocation peut entraîner un déplacement du bloc de mémoire initial vers un autre emplacement dans le tas, ainsi qu'une modification de la taille du bloc de mémoire. La partie utilisateur du bloc contient la valeur 0xCD et les mémoires tampons de remplacement contiennent 0xFD.  
  
 `_aligned_recalloc_dbg` affecte à `errno` la valeur `ENOMEM` si une allocation de mémoire échoue ; la valeur `EINVAL` est retournée si la quantité de mémoire nécessaire (y compris la surcharge mentionnée précédemment) dépasse `_HEAP_MAXREQ`. Pour plus d’informations sur ces codes d’erreur et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 De plus, `_aligned_recalloc_dbg` valide ses paramètres. Si `alignment` n’est pas une puissance de 2, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte la valeur `errno` à `EINVAL`.  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_recalloc_dbg`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)