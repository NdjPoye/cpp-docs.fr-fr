---
title: _query_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_handler
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
- _query_new_handler
- query_new_handler
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
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
ms.openlocfilehash: d79c8a5d68f7dd41a737111a3abe943389bfedd2
ms.lasthandoff: 02/24/2017

---
# <a name="querynewhandler"></a>_query_new_handler
Retourne l’adresse de la routine de nouveau gestionnaire actuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_PNH _query_new_handler(  
   void   
);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne l’adresse de la routine de nouveau gestionnaire actuelle telle que définie par `_set_new_handler`.  
  
## <a name="remarks"></a>Notes  
 La fonction C++ `_query_new_handler` retourne l’adresse de la fonction de gestion des exceptions actuelle définie par la fonction C++ [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). `_set_new_handler` permet de spécifier la fonction de gestion des exceptions qui doit prendre le contrôle si l’opérateur **new** ne parvient pas allouer de la mémoire. Pour plus d’informations, consultez la description des [opérateurs new et delete](../../cpp/new-and-delete-operators.md) dans la Référence du langage C++.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_query_new_handler`|\<new.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)
