---
title: "Cr&#233;ation d&#39;un contr&#244;le de zone de liste d&#233;roulante &#233;tendue | Microsoft Docs"
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
  - "CComboBoxEx (classe), créer des contrôles de zone de liste déroulante étendue"
  - "zones de liste déroulante étendues"
  - "zones de liste déroulante étendues, créer"
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un contr&#244;le de zone de liste d&#233;roulante &#233;tendue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comment le contrôle de zone de liste modifiable étendue est créé selon que vous utilisez le contrôle dans une boîte de dialogue ou le créez dans une fenêtre sans boîte de dialogue.  
  
### Pour utiliser CComboBoxEx directement dans une boîte de dialogue  
  
1.  Dans l'éditeur de boîtes de dialogue, ajoutez un contrôle zone de liste modifiable étendue à la ressource modèle de la boîte de dialogue.  Spécifiez son ID de contrôle  
  
2.  Spécifiez tous les styles requis, à l'aide de la boîte de dialogue Propriétés du contrôle zone de liste modifiable étendue.  
  
3.  Utilisez [Assistant d'Ajout de variable membre](../ide/adding-a-member-variable-visual-cpp.md) pour ajouter une variable membre de type [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) à la propriété de contrôle.  Vous pouvez utiliser ce membre pour appeler des méthodes `CComboBoxEx`.  
  
4.  Utilisez la fenêtre Propriétés pour mapper les fonctions de handler dans la classe de la boîte de dialogue pour tous les messages de notification de contrôle de liste modifiable étendue que vous devez traiter \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
5.  Dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md), définissez les styles supplémentaires pour l'objet `CComboBoxEx`.  
  
### Pour utiliser CComboBoxEx dans une fenêtre boîte sans dialogue.  
  
1.  Définissez le contrôle d'une classe vue ou fenêtre.  
  
2.  Appelez la fonction membre [Créer](../Topic/CTabCtrl::Create.md) du contrôle, éventuellement dans [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), éventuellement dès la fonction gestionnaire [OnCreate](../Topic/CWnd::OnCreate.md) parente de la fenêtre.  Définissez les styles pour le contrôle.  
  
## Voir aussi  
 [Utilisation de CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Contrôles](../mfc/controls-mfc.md)