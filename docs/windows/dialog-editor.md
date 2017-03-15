---
title: "Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.dialog"
  - "vc.editors.dialog.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource editors, Dialog editor"
  - "editors, dialog boxes"
  - "Dialog editor"
  - "dialog boxes, editing"
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'Éditeur de boîtes de dialogue vous permet de créer et de modifier des ressources de boîte de dialogue. Pour ouvrir l'Éditeur de boîtes de dialogue, double\-cliquez sur le fichier .rc d'une boîte de dialogue dans la fenêtre Affichage des ressources \(**Affichage &#124; Affichage des ressources**\). Notez que l'Affichage des ressources n'est pas disponible dans les éditions Express.  
  
 L'une des premières étapes de la création d'une boîte de dialogue \(ou d'un modèle de boîte de dialogue\) consiste à ajouter des contrôles à la boîte de dialogue. Dans l'Éditeur de boîtes de dialogue, vous pouvez organiser les contrôles pour les ajuster à une taille, une forme ou un alignement particulier, ou vous pouvez les déplacer pour travailler dans la boîte de dialogue. Vous pouvez aussi facilement supprimer un contrôle.  
  
 Vous pouvez stocker une boîte de dialogue en tant que modèle pour pouvoir la réutiliser. Vous pouvez aussi facilement basculer entre la conception de la boîte de dialogue et la modification du code qui l'implémente.  
  
 Il est également possible de modifier les propriétés d'un ou plusieurs contrôles dans l'Éditeur de boîtes de dialogue. Vous pouvez changer l'ordre de tabulation, c'est\-à\-dire l'ordre en fonction duquel les contrôles obtiennent le focus quand la touche Tab est enfoncée ou vous pouvez définir une touche d'accès rapide \(combinaison de touches\) qui permet aux utilisateurs de choisir un contrôle en utilisant le clavier. Pour obtenir une liste des touches d'accès rapide prédéfinies, consultez [Touches accélérateur pour l'Éditeur de boîtes de dialogue](../mfc/accelerator-keys-for-the-dialog-editor.md).  
  
 L'Éditeur de boîtes de dialogue vous permet également d'utiliser des contrôles personnalisés, y compris des contrôles ActiveX. En outre, vous pouvez modifier un [mode formulaire](../mfc/reference/cformview-class.md), des [vues d'enregistrements](../data/record-views-mfc-data-access.md) ou des [barres de boîte de dialogue](../mfc/dialog-bars.md).  
  
 À compter de [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)], l’Éditeur de boîtes de dialogue vous permet de définir des dispositions dynamiques qui spécifient comment déplacer et redimensionner des contrôles quand l’utilisateur redimensionne une boîte de dialogue. Pour plus d’informations, consultez [Disposition dynamique](../mfc/dynamic-layout.md).  
  
-   [Création d’une nouvelle boîte de dialogue](../mfc/creating-a-new-dialog-box.md)  
  
-   [Création d’une boîte de dialogue que les utilisateurs ne peuvent pas quitter au moment de l’exécution](../mfc/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [Affichage ou masquage de la barre d’outils Éditeur de boîtes de dialogue](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [Basculement entre l’Éditeur de boîtes de dialogue et le code](../mfc/switching-between-dialog-box-controls-and-code.md)  
  
-   [Contrôles dans les boîtes de dialogue](../mfc/controls-in-dialog-boxes.md)  
  
-   [Ajout de gestionnaires d’événements pour les contrôles de boîte de dialogue](../mfc/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [Test d’une boîte de dialogue](../mfc/testing-a-dialog-box.md)  
  
-   [Touches accélérateur pour l’Éditeur de boîtes de dialogue](../mfc/accelerator-keys-for-the-dialog-editor.md)  
  
-   [Dépannage de l’Éditeur de boîtes de dialogue](../mfc/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  Quand vous utilisez l’Éditeur de boîtes de dialogue, dans de nombreux cas, vous pouvez cliquer sur le bouton droit pour afficher un menu contextuel des commandes fréquemment utilisées.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Resource Editors](../mfc/resource-editors.md)   
 [Contrôles](../mfc/controls-mfc.md)   
 [Classes de contrôle](../mfc/control-classes.md)   
 [Classes de boîte de dialogue](../mfc/dialog-box-classes.md)   
 [Contrôles de boîtes de dialogue et types de variables](../ide/dialog-box-controls-and-variable-types.md)