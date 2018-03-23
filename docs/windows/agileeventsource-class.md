---
title: Classe de AgileEventSource | Documents Microsoft
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d025fc2be86fb5b59107d1deee39962c3c6db04
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="agileeventsource-class"></a>Classe de AgileEventSource
Représente un événement agile. Hérite de [EventSource](eventsource-class.md) et remplace le `Add` fonction membre avec un paramètre de type supplémentaires pour spécifier des options pour l’appel de l’événement agile.
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `TDelegateInterface`  
 L’interface d’un délégué qui représente un gestionnaire d’événements.

 `TEventSourceOptions` Un [InvokeModeOptions](invokemodeoptions-structure.md) structure dont le champ invokeMode a la valeur `InvokeMode::StopOnFirstError` ou `InvokeMode::FireAll`.

## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[AgileEventSource::Add (méthode)](#add)|Ajoute le Gestionnaire d’événements agile représenté par l’interface de délégué spécifié à l’ensemble des gestionnaires d’événements pour l’objet AgileEventSource en cours.|  

## <a name="add"></a> AgileEventSource::Add (méthode)

Ajoute le Gestionnaire d’événements représenté par l’interface de délégué spécifié à l’ensemble des gestionnaires d’événements pour l’objet source d’événement actuel.

### <a name="syntax"></a>Syntaxe

```cpp
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);
```

### <a name="parameters"></a>Paramètres

*delegateInterface*

Interface à un seul objet délégué, qui représente un gestionnaire d’événements.

*jeton* quand cette opération est terminée, un handle qui représente l’événement. Utiliser ce jeton en tant que paramètre à la méthode Remove() pour ignorer le Gestionnaire d’événements.

### <a name="return-value"></a>Valeur de retour
S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.

## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `EventSource`  
 `AgileEventSource`
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)