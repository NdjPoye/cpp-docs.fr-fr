---
title: "Adding Event Handlers for Dialog Box Controls | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "Dialog editor, adding event handlers to controls"
  - "controls [C++], event handlers"
  - "dialog box controls, events"
  - "event handlers, for dialog box controls"
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Event Handlers for Dialog Box Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour les boîtes de dialogue d'un projet qui sont déjà associées à une classe, vous pouvez tirer parti de certains raccourcis lorsque vous créez des gestionnaires d'événements.  Vous pouvez créer rapidement un gestionnaire pour l'événement de notification du contrôle par défaut ou pour n'importe quel message Windows applicable.  
  
#### Pour créer un gestionnaire pour l'événement de notification du contrôle par défaut  
  
1.  Double\-cliquez sur le contrôle.  L'éditeur de texte s'ouvre.  
  
2.  Ajoutez le code du gestionnaire de notification de contrôle dans l'éditeur de texte.  
  
#### Pour créer un gestionnaire pour les messages Windows applicables  
  
1.  Cliquez sur le contrôle pour lequel vous souhaitez gérer l'événement de notification.  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), cliquez sur le bouton **ControlEvents** pour afficher la liste des événements Windows courants associés à ce contrôle.  Par exemple, le bouton **OK** standard dans la boîte de dialogue **À propos de** répertorie les événements de notification suivants :  
  
     **BN\_CLICKED**  
  
     **BN\_DOUBLECLICKED**  
  
     **BN\_KILLFOCUS**  
  
     **BN\_SETFOCUS**  
  
    > [!NOTE]
    >  Vous pouvez également sélectionner la boîte de dialogue et cliquer sur le bouton **ControlEvents** pour afficher la liste des événements Windows courants pour tous les contrôles contenus dans cette boîte de dialogue.  
  
3.  Dans la fenêtre **Propriétés**, cliquez sur la colonne droite à côté de l'événement à gérer, puis sélectionnez le nom de l'événement de notification proposé \(par exemple, **OnBnClickedOK** gère **BN\_CLICKED**\).  
  
    > [!NOTE]
    >  Vous pouvez également fournir un nom de gestionnaire d'événements de votre choix, plutôt que de sélectionner le nom de gestionnaire d'événements par défaut.  
  
     Une fois que vous avez sélectionné l'événement, Visual Studio ouvre l'éditeur de texte et affiche le code du gestionnaire d'événements.  Par exemple, le code suivant est ajouté pour **OnBnClickedOK** par défaut :  
  
    ```  
    void CAboutDlg::OnBnClickedOk(void)  
    {  
       // TODO: Add your control notification handler code here  
    }  
    ```  
  
 Si vous souhaitez ajouter le gestionnaire d'événements à une classe autre que celle qui implémente la boîte de dialogue, utilisez l'[Assistant Gestionnaire d'événements](../ide/event-handler-wizard.md).  Pour plus d'informations, consultez [Ajout d'un gestionnaire d'événements](../ide/adding-an-event-handler-visual-cpp.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Configuration requise  
 Win32  
  
## Voir aussi  
 [Default Control Events](../mfc/default-control-events.md)   
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [Contrôles de boîtes de dialogue et types de variables](../ide/dialog-box-controls-and-variable-types.md)   
 [Ajout d'une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../mfc/reference/adding-an-mfc-message-handler.md)