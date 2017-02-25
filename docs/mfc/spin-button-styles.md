---
title: "Styles de bouton toupie | Microsoft Docs"
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
  - "CSpinButtonCtrl (classe), styles"
  - "contrôle toupie, styles"
  - "styles, CSpinButtonCtrl"
  - "styles, contrôle toupie"
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Styles de bouton toupie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Plusieurs paramètres pour un bouton de spin \([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\) sont contrôlés par les styles.  Vous pouvez définir les styles suivants dans la fenêtre **Propriétés** dans l'éditeur de boîtes de dialogue.  
  
-   **Orientation** Verticale ou horizontale.  Contrôle l'orientation des boutons de direction.  Associé au style `UDS_HORZ`.  
  
-   **Alignement** détaché, gauche, ou droite.  Contrôle l'emplacement du bouton de spin.  Positionne à gauche et droite le bouton de spin en regard de la fenêtre associée.  La largeur de la fenêtre associée est diminuée pour s'adapter au bouton de spin.  Associé aux styles `UDS_ALIGNLEFT` et `UDS_ALIGNRIGHT`.  
  
-   **Auto Buddy** sélectionne automatiquement la fenêtre précédente dans l'ordre de plan dans une fenêtre associé au bouton de spin.  Dans un modèle de boîte de dialogue, il s'agit du contrôle qui précède la toupie dans l'ordre de tabulation.  Associé au style `UDS_AUTOBUDDY`.  
  
-   **Set Buddy Integer** Provoque l'incrémentation et la décrémentation par le contrôle de spin de la légende de la fenêtre associé lorsque la position actuelle change.  Associé au style `UDS_SETBUDDYINT`.  
  
-   **No Thousands** n'insère pas le séparateur de milliers dans la valeur de la légende de la fenêtre associée.  Associé au style `UDS_NOTHOUSANDS`.  
  
    > [!NOTE]
    >  Définissez ce style si vous souhaitez utiliser l'échange de données de boîtes de dialogue \(DDX\) pour obtenir la valeur entière du contrôle associé.  `DDX_Text` n'accepte pas les séparateurs de milliers incorporés.  
  
-   **Retour à la ligne** Provoque que la position de la forme « encapsule » quand une valeur est incrémentée ou décrémentée au delà de la plage du contrôle.  Associé au style `UDS_WRAP`.  
  
-   **Arrow Keys** Provoque que le bouton de spin incrémente ou décrémente la position lorsque les touches de direction BAS et HAUT sont appuyées.  Associé au style `UDS_ARROWKEYS`.  
  
## Voir aussi  
 [Utilisation de CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)