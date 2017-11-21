---
title: _query_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _query_new_handler
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
dev_langs: C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b245286294a74718b7527728d5d9e8dea9793234
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)