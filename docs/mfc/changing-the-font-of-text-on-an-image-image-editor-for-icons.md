---
title: "Changing the Font of Text on an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "fonts, changing on an image"
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Font of Text on an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La procédure ci\-après constitue un exemple qui indique comment :  
  
-   ajouter du texte à une icône dans une application Windows ;  
  
-   manipuler la police de votre texte.  
  
### Pour modifier la police du texte d'une image  
  
1.  Créez une application Windows Forms C\+\+.  Pour plus d'informations, consultez [Création d'un projet d'application Windows](http://msdn.microsoft.com/fr-fr/b2f93fed-c635-4705-8d0e-cf079a264efa).  Le [modèle Application Windows Forms](http://msdn.microsoft.com/fr-fr/1babdebf-ab3f-4a64-a608-98499a5b9cea) ajoute par défaut un fichier nommé app.ico à votre projet.  
  
2.  Dans l'Explorateur de solutions, double\-cliquez sur le fichier app.ico.  L'[Éditeur d'images](../mfc/image-editor-for-icons.md) s'ouvrira.  
  
3.  Dans le menu **Image**, sélectionnez **Outils**, puis **Outil texte**.  La [boîte de dialogue Outil texte](../mfc/text-tool-dialog-box-image-editor-for-icons.md) s'affiche.  
  
4.  Dans la boîte de dialogue Outil texte, tapez `C++` dans la zone de texte vide.  Ce texte apparaît dans une zone redimensionnable localisée dans le coin supérieur gauche du fichier app.ico, dans l'Éditeur d'images.  
  
5.  Dans l'Éditeur d'images, faites glisser la zone redimensionnable au centre du fichier app.ico pour améliorer la lisibilité de votre texte.  
  
6.  Dans la boîte de dialogue Outil texte, cliquez sur le bouton **Police**.  La [boîte de dialogue Police de l'outil texte](../mfc/text-tool-font-dialog-box-image-editor-for-icons.md) s'affiche.  
  
7.  Dans la boîte de dialogue Police de l'outil texte, sélectionnez **Times New Roman** dans la zone de liste **Police** qui répertorie les polices disponibles.  
  
8.  Sélectionnez **Gras** dans la zone de liste **Style de police** qui répertorie les styles de police disponibles.  
  
9. Sélectionnez **10** dans la zone de liste **Taille** qui répertorie les tailles disponibles en points.  
  
10. Cliquez sur le bouton **OK**.  La boîte de dialogue Police de l'outil texte se ferme et les nouveaux paramètres de police s'appliquent à votre texte.  
  
11. Cliquez sur le bouton **Fermer** dans la boîte de dialogue Outil texte.  La zone redimensionnable autour de votre texte disparaît de l'Éditeur d'images.  
  
## Voir aussi  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Toolbar](../mfc/toolbar-image-editor-for-icons.md)