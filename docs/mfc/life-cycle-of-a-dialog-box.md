---
title: "Cycle de vie d&#39;une bo&#238;te de dialogue | Microsoft Docs"
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
  - "boîtes de dialogue, cycle de vie"
  - "cycle de vie des boîtes de dialogue"
  - "boîtes de dialogue MFC, cycle de vie"
  - "boîtes de dialogue modales, cycle de vie"
  - "boîtes de dialogue non modales, cycle de vie"
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cycle de vie d&#39;une bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Au cours du cycle de vie d'une boîte de dialogue, l'utilisateur appelle la boîte de dialogue, en général dans un gestionnaire de commandes qui crée et initialise l'objet du dialogue, l'utilisateur interagit avec la boîte de dialogue, puis la boîte de dialogue se ferme.  
  
 Pour les boîtes de dialogue modales, le gestionnaire rassemble toutes les données que l'utilisateur a entré une fois que la boîte de dialogue se ferme.  Comme l'objet DIALOG existe après que sa fenêtre de dialogue se soit fermée, vous pouvez simplement utiliser les variables membres de la classe de la boîte de dialogue pour extraire les données.  
  
 Pour les boîtes de dialogue non modales, vous pouvez souvent extraire des données de l'objet DIALOG lorsque la boîte de dialogue est toujours visible.  À un certain stade, l'objet DIALOG est détruit ; le moment où cela se produit dépend de votre code.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Création et affichage de boîtes de dialogue](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Création de boîtes de dialogue modales](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Création de boîtes de dialogue non modales](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [Utilisation d'un modèle de boîte de dialogue en mémoire](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [Définition de la couleur d'arrière\-plan de la boîte de dialogue](../mfc/setting-the-dialog-box’s-background-color.md)  
  
-   [Initialisation de la boîte de dialogue](../mfc/initializing-the-dialog-box.md)  
  
-   [Traitement des messages Windows dans votre boîte de dialogue](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [Récupérer des données d'un objet dialogue](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [Fermeture de la boîte de dialogue](../mfc/closing-the-dialog-box.md)  
  
-   [Destruction de la boîte de dialogue](../mfc/destroying-the-dialog-box.md)  
  
-   [Échange \(DDX\) et validation \(DDV\) de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Boîtes de dialogue de feuille de propriétés](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)