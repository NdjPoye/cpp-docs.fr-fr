---
title: _query_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_mode
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
- query_new_mode
- _query_new_mode
dev_langs:
- C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
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
ms.openlocfilehash: 38b5022412f3f07806fcb7a2cea373457c8b405f
ms.lasthandoff: 02/24/2017

---
# <a name="querynewmode"></a>_query_new_mode
Retourne un entier indiquant le mode de nouveau gestionnaire défini par `_set_new_mode` pour `malloc`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le mode de nouveau gestionnaire actuel, à savoir 0 ou 1, pour `malloc`. La valeur de retour 1 indique qu’en cas d’échec d’allocation de mémoire, `malloc` appelle la routine de nouveau gestionnaire ; la valeur de retour 0 indique le contraire.  
  
## <a name="remarks"></a>Notes  
 La fonction C++ `_query_new_mode` retourne un entier qui indique le mode de nouveau gestionnaire défini par la fonction C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) pour [malloc](../../c-runtime-library/reference/malloc.md). Le mode de nouveau gestionnaire indique si, en cas d’échec d’allocation de mémoire, `malloc` doit appeler la routine de nouveau gestionnaire, telle qu’elle est définie par [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Par défaut, `malloc` n’appelle pas la routine de nouveau gestionnaire en cas d’échec. Vous pouvez utiliser `_set_new_mode` pour remplacer ce comportement de sorte qu’en cas d’échec, `malloc` appelle la routine de nouveau gestionnaire comme le fait l’opérateur **new** quand il ne parvient pas à allouer de la mémoire. Pour plus d’informations, consultez la description des [opérateurs new et delete](../../cpp/new-and-delete-operators.md) dans la Référence du langage C++.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_query_new_mode`|\<new.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)