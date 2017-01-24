---
title: "EventSource::Add, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::Add"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Add (méthode)"
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::Add, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute le Gestionnaire d’événements représenté par l’interface du délégué spécifié à l’ensemble des gestionnaires d’événements pour l’objet source d’événement en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `delegateInterface`  
 Interface à un objet délégué qui représente un gestionnaire d’événements.  
  
 `token`  
 Lorsque cette opération se termine, un handle qui représente l’événement. Utiliser ce jeton en tant que paramètre à la [Remove()](../windows/eventsource-remove-method.md) méthode d’ignorer le Gestionnaire d’événements.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [EventSource (classe)](../windows/eventsource-class.md)