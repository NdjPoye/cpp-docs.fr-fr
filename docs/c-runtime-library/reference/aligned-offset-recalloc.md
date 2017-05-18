---
title: _aligned_offset_recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
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
ms.openlocfilehash: c2586cdd836795a31e457edcba42292a6901ec6f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc
Modifie la taille d’un bloc de mémoire qui a été alloué avec [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Pointeur de bloc de mémoire actif.  
  
 `num`  
 Nombre d'éléments.  
  
 `size`  
 Longueur en octets de chaque élément.  
  
 `alignment`  
 Valeur de l'alignement, qui doit être un entier à la puissance 2.  
  
 `offset`  
 Décalage dans l'allocation de mémoire pour forcer l'alignement.  
  
## <a name="return-value"></a>Valeur de retour  
 `_aligned_offset_recalloc` retourne un pointeur void vers le bloc de mémoire réalloué (et éventuellement déplacé). La valeur de retour est `NULL` si la taille est égale à zéro et l'argument de mémoire tampon n'est pas `NULL`, ou si la mémoire disponible est insuffisante pour étendre le bloc à la taille donnée. Dans le premier cas, le bloc d'origine est libéré. Dans le second cas, le bloc d'origine est inchangé. La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet. Pour obtenir un pointeur vers un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
 `_aligned_offset_recalloc` est marqué `__declspec(noalias)` et `__declspec(restrict)`, ce qui signifie que la fonction ne peut pas modifier les variables globales et que le pointeur retourné n'a pas d'alias. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## <a name="remarks"></a>Notes  
 Comme [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_recalloc` autorise une structure à être alignée au niveau d’un décalage au sein de la structure.  
  
 `_aligned_offset_recalloc` est basé sur `malloc`. Pour plus d’informations sur l’utilisation de `_aligned_offset_malloc`, consultez [malloc](../../c-runtime-library/reference/malloc.md). Si `memblock` est `NULL`, la fonction appelle `_aligned_offset_malloc` en interne.  
  
 Cette fonction affecte à `errno` la valeur `ENOMEM` si l’allocation de mémoire a échoué ou si la taille demandée (`num` * `size`) était supérieure à `_HEAP_MAXREQ`. Pour plus d’informations sur `errno`, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). De plus, `_aligned_offset_recalloc` valide ses paramètres. Si `alignment` n’est pas une puissance de 2 ou si `offset` est supérieur ou égal à la taille demandée et différent de zéro, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte la valeur `errno` à `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_recalloc`|\<malloc.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Alignement des données](../../c-runtime-library/data-alignment.md)   
 [_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)
