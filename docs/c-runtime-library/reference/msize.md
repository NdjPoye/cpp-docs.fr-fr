---
title: _msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _msize
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
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 12
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9bc43a31b7e65bfd6ccb5aef83e7fbf7c76edaaf
ms.lasthandoff: 02/24/2017

---
# <a name="msize"></a>_msize
Retourne la taille d’un bloc de mémoire alloué dans le tas.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Pointeur désignant le bloc de mémoire.  
  
## <a name="return-value"></a>Valeur de retour  
 `_msize` retourne la taille (en octets) sous la forme d’un entier non signé.  
  
## <a name="remarks"></a>Notes  
 La fonction `_msize` retourne la taille, en octets, du bloc de mémoire alloué par un appel à `calloc`, `malloc` ou `realloc`.  
  
 Quand l’application est liée à une version de débogage des bibliothèques Runtime C, `_msize` se résout en [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md). Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Cette fonction valide son paramètre. Si `memblock` est un pointeur Null, `_msize` appelle un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’erreur est gérée, la fonction définit `errno` sur `EINVAL` et retourne -1.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
