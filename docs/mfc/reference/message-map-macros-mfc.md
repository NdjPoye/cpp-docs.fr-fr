---
title: "Macros de table des messages (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "démarquer des messages Windows"
  - "macros de table des messages"
  - "plages de table des messages"
  - "macros de mappage des messages"
  - "tables des messages (C++), déclaration et démarcation"
  - "tables des messages (C++), macros"
  - "plages, table des messages"
  - "messages Windows (C++), déclaration"
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Macros de table des messages (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour prendre en charge les tables des messages, MFC fournit les macros suivantes :  
  
### Macros de déclaration et de démarcation des tables des messages  
  
|||  
|-|-|  
|[DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md)|Indique qu'une table des messages est utilisée dans une classe pour mapper des messages aux fonctions \(doit être utilisé dans la déclaration de classe\).|  
|[BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md)|Démarre la définition d'une table de messages \(doit être utilisé dans l'implémentation de classe\).|  
|[END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)|Termine la définition d'une table de messages \(doit être utilisé dans l'implémentation de classe\).|  
  
### macros de mappage des messages  
  
|||  
|-|-|  
|[ON\_COMMAND](../Topic/ON_COMMAND.md)|Indique que la fonction traite un message spécifié de commande.|  
|[ON\_CONTROL](../Topic/ON_CONTROL.md)|Indique quelle fonction traite un message de notification de contrôle personnalisé.|  
|[ON\_MESSAGE](../Topic/ON_MESSAGE.md)|Indique quelle fonction traitera un message défini par l'utilisateur.|  
|[ON\_OLECMD](../Topic/ON_OLECMD.md)|Indique que la fonction gérera une commande de menu d'un DocObject ou son conteneur.|  
|[ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md)|Indique quelle fonction traitera un message enregistré défini par l'utilisateur.|  
|[ON\_REGISTERED\_THREAD\_MESSAGE](../Topic/ON_REGISTERED_THREAD_MESSAGE.md)|Indique que la fonction traite un message défini par l'utilisateur et lorsque vous avez une classe `CWinThread`.|  
|[ON\_THREAD\_MESSAGE](../Topic/ON_THREAD_MESSAGE.md)|Indique que la fonction traite un message défini par l'utilisateur et lorsque vous avez une classe `CWinThread`.|  
|[ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)|Indique quelle la fonction traite un message de commande de mise à jour de l'interface utilisateur.|  
  
### Macros de chaîne de la table des messages  
  
|||  
|-|-|  
|[ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)|Indique que la fonction géreront la plage des ID de commande spécifiées dans les deux premiers paramètres de la macro.|  
|[ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)|Indique que le gestionnaire de mise à jour gérera la plage des ID de commande spécifiés dans les deux premiers paramètres de la macro.|  
|[ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)|Indique que la fonction traite les notifications de la plage des ID de contrôle spécifiés dans les deuxième et troisième paramètres de la macro.  Le premier paramètre est un message de notification contrôle, tel que **BN\_CLICKED**.|  
  
 Pour plus d'informations sur les tables des messages, les macros\-instructions de déclaration de table des messages et de démarcation, et les macros\-instructions de message\- mappage, consultez [Tables des messages](../../mfc/reference/message-maps-mfc.md) et [Rubriques de gestion des messages et de mappage](../../mfc/message-handling-and-mapping.md).  Pour plus d'informations sur les séries de message de mappage, consultez [Gestionnaires pour les plages de table des messages](../../mfc/handlers-for-message-map-ranges.md).  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)