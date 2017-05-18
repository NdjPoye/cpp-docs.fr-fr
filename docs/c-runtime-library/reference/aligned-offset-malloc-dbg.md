---
title: _aligned_offset_malloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
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
ms.openlocfilehash: fb6714506013bcaf9e4d5f6064d7bb98f8e56562
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg
Alloue de la mémoire sur une limite d’alignement spécifiée (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `size`  
 Taille de l'allocation de mémoire demandée.  
  
 [in] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 [in] `offset`  
 Décalage dans l'allocation de mémoire pour forcer l'alignement.  
  
 [in] `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou NULL.  
  
 [in] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou NULL.  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers le bloc de mémoire qui a été alloué ou `NULL` si l'opération a échoué.  
  
## <a name="remarks"></a>Notes  
 `_aligned_offset_malloc_dbg` est une version de débogage de la fonction [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_aligned_offset_malloc_dbg` est réduit à un appel à `_aligned_offset_malloc`. `_aligned_offset_malloc` et `_aligned_offset_malloc_dbg` allouent toutes deux un bloc de mémoire dans le tas de base, mais `_aligned_offset_malloc_dbg` propose plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d’allocation spécifiques et des informations `filename`/`linenumber` pour déterminer l’origine des demandes d’allocation.  
  
 `_aligned_offset_malloc_dbg` alloue le bloc de mémoire avec un peu plus d'espace que la valeur `size` demandée. L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en-têtes de débogage et les mémoires tampons de remplacement. Quand le bloc est alloué, la partie utilisateur du bloc est renseignée avec la valeur 0xCD et chaque mémoire tampon de remplacement est renseignée avec la valeur 0xFD.  
  
 `_aligned_offset_malloc_dbg` est utile quand l’alignement est nécessaire sur un élément imbriqué, par exemple, sur une classe imbriquée.  
  
 `_aligned_offset_malloc_dbg` est basé sur `malloc` ; pour plus d’informations, consultez [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Cette fonction affecte à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée était supérieure à `_HEAP_MAXREQ`. Pour plus d’informations sur `errno`, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). De plus, `_aligned_offset_malloc` valide ses paramètres. Si `alignment` n’est pas une puissance de 2 ou si `offset` est supérieur ou égal à `size` et différent de zéro, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte la valeur `errno` à `EINVAL`.  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Pour plus d’informations sur les types de blocs d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
