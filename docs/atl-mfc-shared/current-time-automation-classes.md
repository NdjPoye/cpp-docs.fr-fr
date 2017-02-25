---
title: "Current Time: Automation Classes | Microsoft Docs"
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
  - "Automation classes, heure actuelle"
  - "heure actuelle, COleDateTime object"
  - "procédures, getting current time"
  - "heure, getting current"
  - "heure, setting current"
ms.assetid: cc967f17-1189-4cf3-85f9-1969462d5f72
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Current Time: Automation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La procédure suivante montre comment créer un objet d' `COleDateTime` et l'initialiser avec l'heure actuelle.  
  
#### Pour obtenir l'heure actuelle  
  
1.  Créez un objet `COleDateTime`.  
  
2.  Appelez `GetCurrentTime`.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/CPP/current-time-automation-classes_1.cpp)]  
  
## Voir aussi  
 [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md)