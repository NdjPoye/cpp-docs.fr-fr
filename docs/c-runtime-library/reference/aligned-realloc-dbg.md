---
title: _aligned_realloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_realloc_dbg
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
- aligned_realloc_dbg
- _aligned_realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_realloc_dbg function
- aligned_realloc_dbg function
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: b5a0a5af02dffea95471a41b9c7bc9726e6beab5
ms.lasthandoff: 02/24/2017

---
# <a name="alignedreallocdbg"></a>_aligned_realloc_dbg
Modifie la taille d’un bloc de mémoire qui a été alloué avec [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void * _aligned_realloc_dbg(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `memblock`  
 Pointeur de bloc de mémoire actif.  
  
 [in] `size`  
 Taille de l'allocation de mémoire demandée.  
  
 [in] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 [in] `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération `realloc` ou NULL.  
  
 [in] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération `realloc` a été demandée ou NULL.  
  
## <a name="return-value"></a>Valeur de retour  
 `_aligned_realloc_dbg` retourne un pointeur void vers le bloc de mémoire réalloué (et éventuellement déplacé). La valeur de retour est `NULL` si la taille est égale à zéro et l'argument de mémoire tampon n'est pas `NULL`, ou si la mémoire disponible est insuffisante pour étendre le bloc à la taille donnée. Dans le premier cas, le bloc d'origine est libéré. Dans le second cas, le bloc d'origine est inchangé. La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet. Pour obtenir un pointeur vers un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
 Le fait de réallouer la mémoire et de modifier l'alignement d'un bloc constitue une erreur.  
  
## <a name="remarks"></a>Notes  
 `_aligned_realloc_dbg` est une version de débogage de la fonction [_aligned_realloc](../../c-runtime-library/reference/aligned-realloc.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_aligned_realloc_dbg` est réduit à un appel à_`aligned_realloc`. \_`aligned_realloc` et `_aligned_realloc_dbg` réallouent toutes deux un bloc de mémoire dans le tas de base, mais `_aligned_realloc_dbg` gère plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d’allocation spécifiques et des informations `filename`/`linenumber` pour déterminer l’origine des demandes d’allocation.  
  
 `_aligned_realloc_dbg` réalloue le bloc de mémoire spécifié avec un peu plus d'espace que la valeur `newSize` demandée. `newSize` peut être inférieure ou supérieure à la taille du bloc de mémoire alloué initialement. L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en-têtes de débogage et les mémoires tampons de remplacement. La réallocation peut entraîner un déplacement du bloc de mémoire initial vers un emplacement différent dans le tas, ainsi qu'une modification de la taille du bloc de mémoire. Si le bloc de mémoire est déplacé, son contenu d'origine est remplacé.  
  
 `_aligned_realloc_dbg` affecte la valeur `errno` à `ENOMEM` si une allocation de mémoire échoue ou si la quantité de mémoire nécessaire (y compris la surcharge mentionnée précédemment) dépasse `_HEAP_MAXREQ`. Pour obtenir des informations sur ce code de retour et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 De plus, `_aligned_realloc_dbg` valide ses paramètres. Si `alignment` n’est pas une puissance de 2, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte la valeur `errno` à `EINVAL`.  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_realloc_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
