---
title: "Tables de r&#233;cepteurs d&#39;&#233;v&#233;nements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables de récepteurs d'événements"
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Tables de r&#233;cepteurs d&#39;&#233;v&#233;nements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un contrôle OLE incorporé déclenche un événement, le contrôle du conteneur reçoit l'événement grâce à un mécanisme, appelé « table de récepteurs d'événements, » fourni par MFC.  Cette table de récepteurs d'événements indique les fonctions gestionnaires pour chaque événement donné, ainsi que les paramètres de ces événements.  Pour plus d'informations sur les tables de récepteurs d'événements, consultez l'article [Conteneurs de contrôle ActiveX](../../mfc/activex-control-containers.md).  
  
### Tables de récepteurs d'événements  
  
|||  
|-|-|  
|[BEGIN\_EVENTSINK\_MAP](../Topic/BEGIN_EVENTSINK_MAP.md)|Démarre la définition d'une table de récepteurs d'événements.|  
|[DECLARE\_EVENTSINK\_MAP](../Topic/DECLARE_EVENTSINK_MAP.md)|Déclare une table de récepteurs d'événements.|  
|[END\_EVENTSINK\_MAP](../Topic/END_EVENTSINK_MAP.md)|Termine la définition d'une table de récepteurs d'événements.|  
|[ON\_EVENT](../Topic/ON_EVENT.md)|Définit un gestionnaire d'événements pour un événement donné.|  
|[ON\_EVENT\_RANGE](../Topic/ON_EVENT_RANGE.md)|Définit un gestionnaire d'événements pour un événement particulier déclenché par un ensemble de contrôles OLE.|  
|[ON\_EVENT\_REFLECT](../Topic/ON_EVENT_REFLECT.md)|Reçoit les événements déclenchés par le contrôle avant qu'ils soient gérés par le conteneur du contrôle.|  
|[ON\_PROPNOTIFY](../Topic/ON_PROPNOTIFY.md)|Définit un gestionnaire pour gérer les notifications de propriété d'un contrôle OLE.|  
|[ON\_PROPNOTIFY\_RANGE](../Topic/ON_PROPNOTIFY_RANGE.md)|Définit un gestionnaire pour gérer les notifications de propriété d'un ensemble de contrôles OLE.|  
|[ON\_PROPNOTIFY\_REFLECT](../Topic/ON_PROPNOTIFY_REFLECT.md)|Reçoit les notifications de propriété envoyées par le contrôle qu'ils soient gérés par le conteneur du contrôle.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)