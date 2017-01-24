---
title: "Menu Image (&#201;diteur d&#39;images pour les ic&#244;nes) | Microsoft Docs"
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
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "menu Image"
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Menu Image (&#201;diteur d&#39;images pour les ic&#244;nes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le menu Image, qui s'affiche uniquement lorsque l'Éditeur d'images est actif, contient des commandes pour modifier les images, gérer les palettes de couleurs et définir les options de la fenêtre Éditeur d'images.  De plus, les commandes pour utiliser les images de périphérique sont disponibles lorsque vous utilisez des icônes et des curseurs.  
  
 **Inverser les couleurs**  
 Inverse vos couleurs.  Pour plus d'informations, consultez [Inversion des couleurs dans une sélection](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md).  
  
 **Retourner horizontalement**  
 Retourne l'image ou la sélection horizontalement.  Pour plus d'informations, consultez [Retournement d'une image](../mfc/flipping-an-image-image-editor-for-icons.md).  
  
 **Retourner verticalement**  
 Retourne l'image ou la sélection verticalement.  Pour plus d'informations, consultez [Retournement d'une image](../mfc/flipping-an-image-image-editor-for-icons.md).  
  
 **Faire pivoter de 90 degrés**  
 Fait pivoter l'image ou la sélection de 90 degrés.  Pour plus d'informations, consultez [Retournement d'une image](../mfc/flipping-an-image-image-editor-for-icons.md).  
  
 **Afficher la fenêtre des couleurs**  
 Ouvre la [fenêtre Couleurs](../windows/colors-window-image-editor-for-icons.md), dans laquelle vous pouvez choisir les couleurs à utiliser pour votre image.  Pour plus d'informations, consultez [Utilisation des couleurs](../mfc/working-with-color-image-editor-for-icons.md).  
  
 **Utiliser la sélection comme pinceau**  
 Vous permet de créer un pinceau personnalisé à partir d'une partie d'une image.  Votre sélection devient un pinceau personnalisé qui distribue les couleurs dans la sélection sur l'image.  Des copies de la sélection sont déposées le long du chemin de déplacement.  Plus vous faites glisser lentement, plus le nombre de copies est important.  Pour plus d'informations, consultez [Création d'un pinceau personnalisé](../mfc/creating-a-custom-brush-image-editor-for-icons.md).  
  
 **Copier et entourer la sélection**  
 Crée une copie de la sélection actuelle et met un contour.  Si la couleur de fond est contenue dans la sélection en cours, celle\-ci sera exclue si l'option [transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) est sélectionnée.  
  
 **Affiner les couleurs**  
 Ouvre le [sélecteur de couleurs personnalisées](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), qui vous permet de personnaliser les couleurs à utiliser pour votre image.  Pour plus d'informations, consultez [Personnalisation ou modification des couleurs](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 **Charger la palette**  
 Ouvre la [boîte de dialogue Charger la palette](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), qui vous permet de charger les couleurs de la palette précédemment enregistrée sous la forme d'un fichier .pal.  
  
 **Enregistrer la palette**  
 Enregistre les couleurs de la palette dans un fichier .pal.  
  
 **Dessin opaque**  
 Lorsque cette option est sélectionnée, la sélection actuelle devient opaque.  Lorsque cette option est désactivée, la sélection actuelle devient transparente.  Pour plus d'informations, consultez [Choix d'un arrière\-plan transparent ou opaque](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 **Éditeur de barres d'outils**  
 Ouvre la [boîte de dialogue Nouvelle ressource de barre d'outils](../mfc/new-toolbar-resource-dialog-box.md).  
  
 **Paramètres de la grille**  
 Ouvre la [boîte de dialogue Paramètres de la grille](../mfc/grid-settings-dialog-box-image-editor-for-icons.md) dans laquelle vous pouvez spécifier des grilles pour votre image.  
  
 **Nouveau type d'image**  
 Ouvre la [boîte de dialogue Nouveau type d'image \<périphérique\>](../mfc/new-device-image-type-dialog-box-image-editor-for-icons.md).  Une seule ressource icône peut contenir plusieurs images de tailles différentes ; Windows peut utiliser la taille d'icône appropriée en fonction de la façon dont elle va être affichée.  Un nouveau type de périphérique ne modifie pas la taille de l'icône, mais crée une nouvelle image à l'intérieur de l'icône.  S'applique uniquement aux icônes et aux curseurs.  
  
 **Types d'images icônes\/curseur en cours**  
 Ouvre un sous\-menu qui répertorie les premières images curseur ou icône disponibles \(les neuf premières\).  La dernière commande du sous\-menu, **Plus...**, ouvre la [boîte de dialogue Ouvrir l'image \<périphérique\>](../mfc/open-device-image-dialog-box-image-editor-for-icons.md).  
  
 **Supprimer le type d'image**  
 Supprime l'image du périphérique sélectionné.  
  
 **Outils**  
 Lance un sous\-menu contenant tous les outils disponibles dans la [barre d'outils Éditeur d'images](../mfc/toolbar-image-editor-for-icons.md).  
  
## Configuration requise  
 Aucun  
  
## Voir aussi  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)