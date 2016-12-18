---
title: "Notifications envoy&#233;es par les contr&#244;les d&#39;animation | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles animation (C++), notifications"
  - "CAnimateCtrl (classe), notifications"
  - "contrôles (MFC), animation"
  - "notifications, contrôles animation"
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Notifications envoy&#233;es par les contr&#244;les d&#39;animation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un outil d'animations \([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)\) a deux types différents de messages de notification.  Les notifications sont envoyées sous forme de messages [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591).  
  
 Le message [ACN\_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) est envoyé lorsque le contrôle animations a commencé jouer un clip.  Le message [ACN\_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) est envoyé lorsque le contrôle animations est terminée ou arrêté de jouer un clip.  
  
## Voir aussi  
 [Utilisation de CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)