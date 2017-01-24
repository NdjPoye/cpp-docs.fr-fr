---
title: "Utilisation de CSpinButtonCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl (classe), utilisation"
  - "contrôle toupie"
  - "contrôles up-down"
  - "contrôles up-down, contrôle toupie"
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de CSpinButtonCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le contrôle *bouton de spin* \(également appelé contrôle *inversion*\)  fournit une paire de flèches sur lesquelle un utilisateur peut cliquer pour paramétrer une valeur.  Cette valeur est appelée *position actuelle*.  La position reste dans la plage du bouton de spin.  Lorsque l'utilisateur clique sur la flèche haut, la position se déplace vers le maximum ; et lorsque l'utilisateur clique sur la flèche vers le bas, la position déplace vers le minimum.  
  
 Le contrôle de bouton de spin est représenté dans MFC par la classe [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md).  
  
> [!NOTE]
>  Par défaut, la plage du bouton de spin a la valeur maximale définie à zéro \(0\) et la valeur minimale 100.  Étant donné que la valeur maximale est inférieure à la valeur minimale, cliquez sur la flèche haut pour diminuer la position et cliquez sur la flèche bas pour l'augmenter.  Utilisez [CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md) pour ajuster ces valeurs.  
  
 En général, la position actuelle est affichée dans un contrôle assistant.  Le contrôle assistant est appelé *fenêtre compagnon*.  Pour une figure d'un contrôle de spin, consultez [À propos de contrôle up\-down](http://msdn.microsoft.com/library/windows/desktop/bb759889) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Pour créer un contrôle de spin et une fenêtre compagnon de contrôle d'édition, dans Visual Studio, faites glisser d'abord un contrôle d'édition dans la boîte de dialogue ou dans la fenêtre, puis faites glisser à son tour un contrôle de spin.  Sélectionnez le contrôle de spin et définissez ses propriétés **Compagnon Automatique** et **Définir l'entier compagnon** sur **Vrai**.  Définissez également la propriété **Alignement** ; **Aligner à droite** est le plus commun.  Avec ces paramètres, le contrôle de version est défini comme fenêtre compagnon car il précède directement le contrôle d'édition dans l'ordre de tabulation.  Le contrôle d'édition affiche des entiers et le contrôle de spin est incorporé dans la partie droite du contrôle d'édition.  Éventuellement, vous pouvez définir la plage valide du contrôle de spin à l'aide de la méthode [CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md).  Aucun gestionnaire d'événements n'est requis pour la communication entre le contrôle de spin et la fenêtre compagnon car ils échangent des données directement.  Si vous utilisez un contrôle de spin pour d'autres fins, par exemple, pour paginer dans une séquence de fenêtres ou des boîtes de dialogue, ajoutez un gestionnaire pour le message `UDN_DELTAPOS` et exécutez votre action personnalisée à cet endroit.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Styles de bouton toupie](../mfc/spin-button-styles.md)  
  
-   [Bouton toupie, fonctions membres](../mfc/spin-button-member-functions.md)  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)