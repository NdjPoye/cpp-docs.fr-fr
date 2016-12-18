---
title: "Traitement des messages de notification dans les contr&#244;les de liste | Microsoft Docs"
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
  - "CListCtrl (classe), notifications de traitement"
  - "notifications de traitement"
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des messages de notification dans les contr&#244;les de liste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand les utilisateurs cliquent sur des en\-têtes de colonne, font glisser des icônes, éditent des étiquettes etc., le contrôle de liste \([CListCtrl](../mfc/reference/clistctrl-class.md)\) envoie des messages de notification dans la fenêtre parente.  Traitez ces messages si vous souhaitez effectuer quelque chose en réponse.  Par exemple, lorsque l'utilisateur clique sur un en\-tête de colonne, vous pouvez trier les éléments en fonction du contenu de la colonne sélectionnée, comme dans Microsoft Outlook.  
  
 Traitez les messages **WM\_NOTIFY** du contrôle de liste dans votre classe vue ou boîte de dialogue.  Utilisez la fenêtre Propriétés pour créer une fonction gestionnaire [OnChildNotify](../Topic/CWnd::OnChildNotify.md) avec une instruction SWITCH sur laquelle le message de notification est traité.  
  
 Pour obtenir la liste des notifications qu'un contrôle de liste peut envoyer à la fenêtre parente, consultez [Référence sur les contrôles liste de vue](http://msdn.microsoft.com/library/windows/desktop/bb774737) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)