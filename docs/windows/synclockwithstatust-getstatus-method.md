---
title: "Synclockwithstatust::GetStatus, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 181735766e62aa1bf8c306bd425c6e6b03b2066d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus, méthode
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le résultat d’une opération d’attente sur l’objet qui est basé sur la classe SyncLockWithStatusT, comme un [Mutex](../windows/mutex-class1.md) ou [sémaphore](../windows/semaphore-class.md). Zéro (0) indique que l’opération d’attente retourné à l’état signalé ; Sinon, un autre état s’est produite, telles que la valeur de délai d’attente s’est écoulé.  
  
## <a name="remarks"></a>Notes  
 Récupère l’état d’attente de l’objet SyncLockWithStatusT actuel.  
  
 La fonction GetStatus() récupère la valeur de l’objet sous-jacent [status_](../windows/synclockwithstatust-status-data-member.md) membre de données. Lorsqu’un objet basé sur la classe SyncLockWithStatusT effectue une opération de verrouillage, l’objet attend d’abord l’objet devienne disponible. Le résultat de cette opération d’attente est stocké dans le `status_` membre de données. Les valeurs possibles de le `status_` membre de données sont les valeurs de retour de l’opération d’attente. Pour plus d’informations, consultez les valeurs de retour de la **WaitForSingleObjectEx()** fonction dans la bibliothèque MSDN.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Voir aussi  
 [SyncLockWithStatusT, classe](../windows/synclockwithstatust-class.md)