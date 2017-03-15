---
title: "Utilisation de contr&#244;les Slider | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl (classe), utilisation"
  - "contrôles Slider"
  - "contrôles Slider, utilisation"
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation de contr&#244;les Slider
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation standard d'un curseur de contrôle suit le modèle ci\-dessous:  
  
-   Le contrôle est créé.  Si le contrôle est spécifié dans un modèle de la boîte de dialogue, la création est automatique lorsque la boîte de dialogue est créée. \(Vous devez avoir un membre de [CAnimateCtrl](../mfc/reference/csliderctrl-class.md) dans votre classe de dialogue correspondant au curseur de contrôle.\) Autrement, vous pouvez utiliser la fonction membre [Créer](../Topic/CSliderCtrl::Create.md) pour créer le contrôle comme une fenêtre enfant de n'importe quelle fenêtre.  
  
-   Appelez plusieurs fonctions membres Définir pour définir les valeurs du contrôle.  Les modifications que vous pouvez apporter incluent définir les positions des valeurs minimale et maximale pour le curseur, ajouter les graduations, définir une plage de sélection, et repositionner le curseur.  Pour les contrôles dans une boîte de dialogue, le bon moment pour le faire est dans la fonction [OnInitDialog](../Topic/CDialog::OnInitDialog.md) de la boîte de dialogue.  
  
-   Lorsque l'utilisateur interagit avec le contrôle, il envoie des messages de notification.  Vous pouvez extraire la valeur de curseur du contrôle en appelant la fonction membre d' [GetPos](../Topic/CSliderCtrl::GetPos.md).  
  
-   Lorsque vous en avez terminé avec le contrôle, vous devez vérifier qu'il est correctement détruit.  Si le curseur de contrôle est dans une boîte de dialogue, lui et l'objet de `CSliderCtrl` sont détruits automatiquement.  Sinon, vous devez vérifier que le flux de contrôle et l'objet `CSliderCtrl` sont correctement détruits.  
  
## Voir aussi  
 [Utilisation de CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)