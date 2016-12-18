---
title: "EventSource::addRemoveLock_, donn&#233;es de membre | Microsoft Docs"
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
  - "event/Microsoft::WRL::EventSource::addRemoveLock_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "addRemoveLock_ (membre de données)"
ms.assetid: e2d69256-4891-4aad-ad0b-76479c0bb076
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::addRemoveLock_, donn&#233;es de membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Synchronise l’accès à la [targets_](../windows/eventsource-targets-data-member.md) tableau lors de l’ajout, suppression ou appeler des gestionnaires d’événements.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Wrappers::SRWLock addRemoveLock_;  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [EventSource (classe)](../windows/eventsource-class.md)