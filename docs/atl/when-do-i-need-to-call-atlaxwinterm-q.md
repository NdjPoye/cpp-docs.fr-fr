---
title: "When Do I Need to Call AtlAxWinTerm? | Microsoft Docs"
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
  - "AtlAxWinTerm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinTerm method"
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 12
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinTerm?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinTerm](../Topic/AtlAxWinTerm.md) annule l'inscription la classe de fenêtre de **"AtlAxWin80"** .  Vous devez appeler cette fonction \(si vous n'avez plus besoin de créer des fenêtres hôte\) après tout existant les fenêtres hôte est perdu.  Si vous n'appelez pas cette fonction, la classe de fenêtre sera annulée l'enregistrement automatiquement lorsque le processus se termine.  
  
## Voir aussi  
 [When Do I Need to Call AtlAxWinInit?](../atl/when-do-i-need-to-call-atlaxwininit-q.md)   
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)