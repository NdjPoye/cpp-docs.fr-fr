---
title: _aligned_msize_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 10449c1d6651f4816e3f1f6ab7c406abc070b7a4
ms.lasthandoff: 02/24/2017

---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg
Retourne la taille d’un bloc de mémoire alloué dans le tas (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t _aligned_msize_dbg(  
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
 Les valeurs `alignment` et `offset` doivent être les mêmes que les valeurs passées à la fonction qui a alloué le bloc.  
  
 `_aligned_msize_dbg` est une version de débogage de la fonction [_aligned_msize](../../c-runtime-library/reference/aligned-msize.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_aligned_msize_dbg` est réduit à un appel à `_aligned_msize`. `_aligned_msize` et `_aligned_msize_dbg` calculent toutes deux la taille d’un bloc de mémoire dans le tas de base, mais `_aligned_msize_dbg` ajoute une fonctionnalité de débogage : elle inclut les mémoires tampons de chaque côté de la partie utilisateur du bloc de mémoire dans la taille retournée.  
  
 Cette fonction valide son paramètre. Si `memblock` est un pointeur null ou que `alignment` n’est pas une puissance de 2, `_msize` appelle un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’erreur est gérée, la fonction définit `errno` sur `EINVAL` et retourne -1.  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)
