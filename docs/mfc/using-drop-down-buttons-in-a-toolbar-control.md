---
title: "Utilisation de boutons de liste d&#233;roulante dans un contr&#244;le ToolBar | Microsoft Docs"
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
  - "TBN_DROPDOWN"
  - "TBSTYLE_EX_DRAWDDARROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl (classe), boutons déroulants"
  - "boutons déroulants dans les barres d'outils"
  - "TBN_DROPDOWN (notification)"
  - "TBSTYLE_EX_DRAWDDARROWS"
  - "barres d'outils (C++), boutons déroulants"
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de boutons de liste d&#233;roulante dans un contr&#244;le ToolBar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Outre les boutons de commande standard, une barre d'outils peut également avoir des boutons déroulants.  Un bouton de liste déroulante est généralement désigné par la présence d'une flèche orientée vers le bas.  
  
> [!NOTE]
>  La flèche vers le bas apparaît uniquement si le style `TBSTYLE_EX_DRAWDDARROWS` étendu a été défini.  
  
 Lorsque l'utilisateur clique sur cette flèche \(ou le bouton lui\-même, si aucune flèche n'est présente\), un message de notification de `TBN_DROPDOWN` est envoyé au parent du contrôle de barre d'outils.  Vous pouvez ensuite traiter la notification et afficher un menu contextuel ; semblable au comportement d'Internet Explorer.  
  
 La procédure suivante montre comment implémenter un bouton de la barre d'outils dans un menu contextuel :  
  
### Pour implémenter un bouton de liste déroulante  
  
1.  Une fois que votre objet de`CToolBarCtrl` a été créé, définissez le style de `TBSTYLE_EX_DRAWDDARROWS`, en utilisant le code suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Définir le style de `TBSTYLE_DROPDOWN` pour chaque bouton nouveau \([InsertButton](../Topic/CToolBarCtrl::InsertButton.md) ou [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)\) ou déjà existant \([SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)\) qui seront des boutons déroulants.  L'exemple suivant illustre la modification d'un bouton existant dans un objet de `CToolBarCtrl` :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Ajoutez un gestionnaire de `TBN_DROPDOWN` à la classe parente de l'objet barre d'outils.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  Dans le gestionnaire, afficher le menu contextuel approprié.  L'exemple de code suivant montre un appel de méthode :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)