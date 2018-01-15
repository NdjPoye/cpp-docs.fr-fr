---
title: "Fonctions globales de la gestion des événements | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlbase/ATL::AtlWaitWithMessageLoop
dev_langs: C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6670ef283d24f57b407ad70693421feae427855f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-global-functions"></a>Fonctions globales de la gestion des événements
Cette fonction fournit un gestionnaire d’événements.  
  
> [!IMPORTANT]
>  La fonction répertoriée dans le tableau suivant ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Attend un objet soit signalé, en attendant la distribution des messages de fenêtre en fonction des besoins.|  

## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 Attend que l'objet soit signalé tout en distribuant les messages de fenêtre en fonction des besoins.  
  
> [!IMPORTANT]
>  Cette fonction ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Paramètres  
 `hEvent`  
 [in] Le handle de l’objet à attendre.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** si l’objet a été signalé.  
  
### <a name="remarks"></a>Notes  
 Cela est utile si vous souhaitez attendre un événement d’un objet à se produire et être averti de ce produit, mais autoriser les messages de fenêtre doit être distribué lors de l’attente.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)
