---
title: _callnewh | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _callnewh
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
- _callnewh
dev_langs:
- C++
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5754a22af15f8eca1d7352e3d172d141447a2ca4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="callnewh"></a>_callnewh
Appelle le *nouveau gestionnaire* installé.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
```  
  
#### <a name="parameters"></a>Paramètres  
 `size`  
 Quantité de mémoire que l’[opérateur new](../../cpp/new-operator-cpp.md) a essayé d’allouer.  
  
## <a name="return-value"></a>Valeur de retour  
  
|Value|Description|  
|-----------|-----------------|  
|0|Échec : aucun nouveau gestionnaire n’est installé ou actif.|  
|1|Réussite : le nouveau gestionnaire est installé et activé. L’allocation de mémoire peut être retentée.|  
  
## <a name="exceptions"></a>Exceptions  
 Cette fonction génère [bad_alloc](../../standard-library/bad-alloc-class.md) si le *nouveau gestionnaire* est introuvable.  
  
## <a name="remarks"></a>Notes  
 Le *nouveau gestionnaire* est appelé si l’[opérateur new](../../cpp/new-operator-cpp.md) ne parvient pas à allouer de la mémoire. Le nouveau gestionnaire peut alors lancer une action appropriée, par exemple la libération de mémoire pour que les allocations suivantes aboutissent.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|_callnewh|internal.h|  
  
## <a name="see-also"></a>Voir aussi  
 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md)