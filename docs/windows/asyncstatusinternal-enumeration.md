---
title: "AsyncStatusInternal (énumération) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd277fecb0bc63d5ee823af98df8aa298b285964
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal (énumération)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Notes  
 Spécifie un mappage entre des énumérations internes pour l’état des opérations asynchrones et la **Windows::Foundation::AsyncStatus** énumération.  
  
## <a name="members"></a>Membres  
 `_Created`  
 Équivalent à :: Windows::Foundation::AsyncStatus :: créé  
  
 `_Started`  
 Équivalent à :: Windows::Foundation::AsyncStatus :: démarré  
  
 `_Completed`  
 Équivalent à :: Windows::Foundation::AsyncStatus :: terminée  
  
 `_Cancelled`  
 Équivalent à :: Windows::Foundation::AsyncStatus :: annulée  
  
 `_Error`  
 Équivalent à :: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** async.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)