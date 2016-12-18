---
title: "Cr&#233;ation du contr&#244;le de s&#233;lecteur de date et heure | Microsoft Docs"
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
  - "CDateTimeCtrl (classe), créer"
  - "DateTimePicker (contrôle) (MFC), créer"
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation du contr&#244;le de s&#233;lecteur de date et heure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comment le contrôle Date Time Picker est dépend de si vous utilisez le contrôle dans une boîte de dialogue ou le créez dans une fenêtre sans boîte de dialogue.  
  
### Pour utiliser CDateTimeCtrl directement dans une boîte de dialogue  
  
1.  Dans l'éditeur de boîtes de dialogue, ajoutez un contrôle Date Time Picker à la ressource de modèle de boîte de dialogue.  Spécifiez son ID de contrôle  
  
2.  Spécifiez tous les styles requis, à l'aide de la boîte de dialogue Propriétés du contrôle Date Time Picker.  
  
3.  Utilisez [Assistant d'Ajout de variable membre](../ide/adding-a-member-variable-visual-cpp.md) pour ajouter une variable membre de type [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) à la propriété de contrôle.  Vous pouvez utiliser ce membre pour appeler des méthodes `CDateTimeCtrl`.  
  
4.  Utilisez la fenêtre Propriétés pour mapper les fonctions de handler dans la classe de la boîte de dialogue pour tous les messages de notification de contrôle dedate time picker control [notification](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) que vous devez traiter \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
5.  Dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md), définissez les styles supplémentaires pour l'objet `CDateTimeCtrl`.  
  
### Pour utiliser CDateTimeCtrl dans une fenêtre boîte sans dialogue.  
  
1.  Déclarez le contrôle d'une classe vue ou fenêtre.  
  
2.  Appelez la méthode [Create](../Topic/CTabCtrl::Create.md) du contrôle, éventuellement dans [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), éventuellement dans la fonction gestionnaire [OnCreate](../Topic/CWnd::OnCreate.md) de la fenêtre parente \(si vous sous\-classez le contrôle\).  Définissez les styles pour le contrôle.  
  
## Voir aussi  
 [Utilisation de CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)