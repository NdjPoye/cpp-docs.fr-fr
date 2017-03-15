---
title: _aligned_msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_msize
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
- _aligned_msize
- aligned_msize
dev_langs:
- C++
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: 6
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
ms.openlocfilehash: 375eb2921ac47be819eeb050fa87643c50a52289
ms.lasthandoff: 02/24/2017

---
# <a name="alignedmsize"></a>_aligned_msize
Retourne la taille d’un bloc de mémoire alloué dans le tas.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t _msize(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `memblock`  
 Pointeur désignant le bloc de mémoire.  
  
 [in] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 [in] `offset`  
 Décalage dans l'allocation de mémoire pour forcer l'alignement.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la taille (en octets) sous la forme d’un entier non signé.  
  
## <a name="remarks"></a>Notes  
 La fonction `_aligned_msize` retourne la taille, en octets, du bloc de mémoire alloué par un appel à [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [_aligned_realloc](../../c-runtime-library/reference/aligned-realloc.md). Les valeurs `alignment` et `offset` doivent être les mêmes que les valeurs passées à la fonction qui a alloué le bloc.  
  
 Quand l’application est liée à une version de débogage des bibliothèques Runtime C, `_aligned_msize` se résout en [_aligned_msize_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md). Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Cette fonction valide son paramètre. Si `memblock` est un pointeur null ou que `alignment` n’est pas une puissance de 2, `_msize` appelle un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’erreur est gérée, la fonction définit `errno` sur `EINVAL` et retourne -1.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)
