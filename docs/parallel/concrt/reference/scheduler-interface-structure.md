---
title: scheduler_interface, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
dev_langs:
- C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a56c36ae0cb4cf7111137351dbd71cc53d73b42a
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerinterface-structure"></a>scheduler_interface, structure
Interface du planificateur  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct __declspec(novtable) scheduler_interface;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[scheduler_interface::Schedule](#schedule)||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `scheduler_interface`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** pplinterface.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="schedule"></a>scheduler_interface::Schedule, méthode  
  
```
virtual void schedule(
    TaskProc_t,
 void*) = 0;
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

