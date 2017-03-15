---
title: "Elapsed Time: Automation Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adding dates"
  - "Automation classes, temps écoulé"
  - "calculating dates and times"
  - "calculs, date et heure"
  - "dates, calculating intervals"
  - "temps écoulé, calculating in Automation"
  - "intervals, date et heure"
  - "heure, elapsed"
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Elapsed Time: Automation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure indique comment calculer la différence entre deux objets d' `CTime` et obtenir un résultat de `CTimeSpan` .  
  
#### Pour calculer le temps écoulé  
  
1.  Créez deux objets d' `COleDateTime` .  
  
2.  Placez l'un des objets d' `COleDateTime` à l'heure actuelle.  
  
3.  Effectuez une tâche longue.  
  
4.  Définissez l'autre objet d' `COleDateTime` à l'heure actuelle.  
  
5.  Prenez la différence entre les deux heures.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/CPP/elapsed-time-automation-classes_1.cpp)]  
  
## Voir aussi  
 [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md)