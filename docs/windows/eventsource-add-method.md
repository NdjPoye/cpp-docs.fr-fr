---
title: "EventSource::Add, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::Add
dev_langs: C++
helpviewer_keywords: Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dca2e67baccfedea10f7faae9ac49ebb0e5bdb14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="eventsourceadd-method"></a>EventSource::Add, méthode
Ajoute le Gestionnaire d’événements représenté par l’interface de délégué spécifié à l’ensemble des gestionnaires d’événements pour l’objet source d’événement actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `delegateInterface`  
 Interface à un seul objet délégué, qui représente un gestionnaire d’événements.  
  
 `token`  
 Lorsque cette opération est terminée, un handle qui représente l’événement. Utiliser ce jeton en tant que paramètre à la [Remove()](../windows/eventsource-remove-method.md) méthode pour supprimer le Gestionnaire d’événements.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [EventSource, classe](../windows/eventsource-class.md)