---
title: "Elapsed Time: General-Purpose Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "calculating dates and times"
  - "calculs, date et heure"
  - "dates, calculating intervals"
  - "temps écoulé"
  - "temps écoulé, calculer"
  - "intervals, date et heure"
  - "heure, elapsed"
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Elapsed Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La procédure suivante montre comment calculer la différence entre deux objets d' `CTime` et obtenir un résultat de `CTimeSpan` .  
  
#### Pour calculer le temps écoulé  
  
1.  Utilisez des objets d' `CTime` et d' `CTimeSpan` pour calculer le temps écoulé, comme suit :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/CPP/elapsed-time-general-purpose-classes_1.cpp)]  
  
     Une fois que vous avez calculé `elapsedTime`, vous pouvez utiliser les fonctions membres d' `CTimeSpan` pour récupérer les composants de la valeur de temps écoulé.  
  
## Voir aussi  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)