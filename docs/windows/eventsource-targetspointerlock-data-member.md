---
title: "EventSource::targetsPointerLock_, donn&#233;es de membre | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::targetsPointerLock_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "targetsPointerLock_ (membre de données)"
ms.assetid: 8f08409f-5262-4be7-9cf1-2ed15f19684a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventSource::targetsPointerLock_, donn&#233;es de membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Synchronise l’accès aux membres de données internes, même lorsque des gestionnaires d’événements pour cette source d’événement sont ajoutés, supprimés ou appelée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Wrappers::SRWLock targetsPointerLock_;  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [EventSource (classe)](../windows/eventsource-class.md)