---
title: "Converting Bitmaps to Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "bitmaps [C++], converting to toolbars"
  - "Toolbar editor, converting bitmaps"
  - "toolbars [C++], converting bitmaps"
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Converting Bitmaps to Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer une nouvelle barre d'outils en convertissant une bitmap.  Le graphique de la bitmap est converti en images de bouton pour une barre d'outils.  En règle générale, la bitmap contient plusieurs images de bouton dans une seule bitmap, avec une image pour chaque bouton.  Les images peuvent être de n'importe quelle taille ; la valeur par défaut est 16 pixels de large et la hauteur de l'image.  Vous pouvez spécifier la taille des images de bouton dans la [boîte de dialogue Nouvelle ressource de barre d'outils](../mfc/new-toolbar-resource-dialog-box.md) lorsque vous choisissez Éditeur de barres d'outils dans le menu **Image** quand vous vous trouvez dans l'Éditeur d'images.  
  
### Pour convertir des bitmaps en barre d'outils  
  
1.  Ouvrez une ressource bitmap existante dans l'[Éditeur d'images](../mfc/image-editor-for-icons.md).  \(Si la bitmap ne se trouve pas déjà dans votre fichier .rc, cliquez avec le bouton droit sur le fichier .rc, choisissez **Importer** dans le menu contextuel, recherchez la bitmap que vous souhaitez ajouter à votre fichier .rc, puis cliquez sur **Ouvrir**.\)  
  
2.  Dans le menu **Image**, choisissez **Éditeur de barres d'outils**.  
  
     La [boîte de dialogue Nouvelle ressource de barre d'outils](../mfc/new-toolbar-resource-dialog-box.md) apparaît.  Vous pouvez changer la largeur et la hauteur des images d'icône afin qu'elles correspondent à celles de la bitmap.  L'image de la barre d'outils s'affiche dans l'Éditeur de barres d'outils.  
  
3.  Pour terminer la conversion, changez l'**ID** de commande du bouton en utilisant la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Tapez le nouvel **ID** ou sélectionnez\-en un dans la liste déroulante **ID**.  
  
    > [!TIP]
    >  La fenêtre Propriétés contient un bouton punaise dans la barre de titre.  Un clic sur ce bouton active ou désactive le masquage automatique de la fenêtre.  Pour parcourir rapidement toutes les propriétés des boutons de barre d'outils sans rouvrir chaque fenêtre Propriétés individuellement, désactivez le masquage automatique afin que la fenêtre Propriétés reste visible.  
  
 Vous pouvez également changer les ID de commande des boutons sur la nouvelle barre d'outils en utilisant la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Pour plus d'informations sur la nouvelle barre d'outils, consultez [Création, déplacement et modification de boutons de barre d'outils](../mfc/creating-moving-and-editing-toolbar-buttons.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 MFC ou ATL  
  
## Voir aussi  
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)