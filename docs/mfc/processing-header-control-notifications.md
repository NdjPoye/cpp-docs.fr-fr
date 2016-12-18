---
title: "Traitement des notifications de contr&#244;le Header | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CHeaderCtrl (classe), notifications de traitement"
  - "contrôles (MFC), header"
  - "notifications de contrôle header"
  - "contrôles header, notifications de traitement"
  - "notifications, traitement pour CHeaderCtrl"
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des notifications de contr&#244;le Header
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la vue ou dans la boîte de dialogue, utilisez la fenêtre Propriétés pour créer une fonction gestionnaire d'[OnChildNotify](../Topic/CWnd::OnChildNotify.md) avec une instruction SWITCH pour tous les messages de notification de contrôle à traiter \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\)  \(voir l'[Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  Les notifications sont envoyées à la fenêtre parente lorsque l'utilisateur clique sur ou double\-clique sur un élément d'en\-tête, faites glisser un diviseur entre les éléments, et ainsi de suite.  
  
 Les messages de notification associée à un contrôle header sont répertoriées dans [Référence de contrôle header](http://msdn.microsoft.com/library/windows/desktop/bb775239) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)