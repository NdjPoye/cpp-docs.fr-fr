---
title: _recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 18c1e36c2671c1c04ae8dd317a14234eda4c09a3
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="recallocdbg"></a>_recalloc_dbg
Réalloue un tableau et initialise ses éléments à 0 (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_recalloc_dbg(   
   void *userData,  
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `userData`  
 Pointeur vers le bloc de mémoire précédemment alloué.  
  
 `num`  
 Nombre de blocs de mémoire demandé.  
  
 `size`  
 Taille de chaque bloc de mémoire demandée (octets).  
  
 `blockType`  
 Type de bloc de mémoire demandé : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details).  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
 Les paramètres `filename` et `linenumber` sont disponibles uniquement quand `_recalloc_dbg` a été appelée explicitement ou que la constante du préprocesseur [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) a été définie.  
  
## <a name="return-value"></a>Valeur de retour  
 Une fois exécutée, cette fonction retourne un pointeur vers la partie utilisateur du bloc de mémoire réalloué, appelle la nouvelle fonction de gestionnaire ou retourne NULL. Pour obtenir une description complète du comportement de retour, voir la section Notes suivante. Pour plus d’informations sur l’utilisation de la fonction de nouveau gestionnaire, voir la fonction [_malloc](../../c-runtime-library/reference/recalloc.md).  
  
## <a name="remarks"></a>Notes  
 `_recalloc_dbg` est une version de débogage de la fonction [_recalloc](../../c-runtime-library/reference/recalloc.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_recalloc_dbg` est réduit à un appel à `_recalloc`. `_recalloc` et `_recalloc_dbg` réallouent toutes deux un bloc de mémoire dans le tas de base, mais `_recalloc_dbg` gère plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d’allocation spécifiques et des informations `filename`/`linenumber` pour déterminer l’origine des demandes d’allocation.  
  
 `_recalloc_dbg` réalloue le bloc de mémoire spécifié avec un peu plus d’espace que la taille demandée (`num` * `size`), ce qui peut donner une taille inférieure ou supérieure à la taille du bloc de mémoire alloué initialement. L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en-têtes de débogage et les mémoires tampons de remplacement. La réallocation peut entraîner un déplacement du bloc de mémoire initial vers un autre emplacement dans le tas, ainsi qu'une modification de la taille du bloc de mémoire. La partie utilisateur du bloc contient la valeur 0xCD et chaque mémoire tampon de remplacement contient 0xFD.  
  
 `_recalloc_dbg` affecte à `errno` la valeur `ENOMEM` si une allocation de mémoire échoue ; la valeur `EINVAL` est retournée si la quantité de mémoire nécessaire (y compris la surcharge mentionnée précédemment) dépasse `_HEAP_MAXREQ`. Pour plus d’informations sur ces codes d’erreur et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_recalloc_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
