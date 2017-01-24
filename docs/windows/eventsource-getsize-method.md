---
title: "EventSource::GetSize, m&#233;thode | Microsoft Docs"
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
  - "event/Microsoft::WRL::EventSource::GetSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSize (méthode)"
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::GetSize, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère le nombre de gestionnaires d’événements associés à l’objet source d’événement en cours  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le nombre de gestionnaires d’événements dans [targets_](../windows/eventsource-targets-data-member.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [EventSource (classe)](../windows/eventsource-class.md)