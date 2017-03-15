---
title: "Defining Member Variables for Dialog Controls | Microsoft Docs"
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
  - "member variables, defining for controls"
  - "variables, dialog box control member variables"
  - "controls [C++], member variables"
  - "Dialog editor, defining member variables for controls"
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Defining Member Variables for Dialog Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour définir une variable membre pour un contrôle de boîte de dialogue à l'exception des boutons, vous pouvez utiliser la méthode suivante.  
  
> [!NOTE]
>  Cet article s'applique uniquement aux contrôles de boîte de dialogue dans un projet MFC.  Les projets ATL doivent utiliser la boîte de dialogue **Nouveaux messages et gestionnaires d'événements Windows**.  
  
### Pour définir une variable membre pour un contrôle de boîte de dialogue \(à l'exception d'un bouton\)  
  
1.  Dans l'[Éditeur de boîtes de dialogue](../mfc/dialog-editor.md), sélectionnez un contrôle.  
  
2.  Tout en maintenant la touche **Ctrl** enfoncée, double\-cliquez sur le contrôle de boîte de dialogue.  
  
     L'[Assistant Ajout de variable membre](../ide/add-member-variable-wizard.md) s'affiche.  
  
3.  Tapez les informations appropriées dans l'Assistant **Ajout d'une variable membre**.  Pour plus d'informations, voir [Échange de données de boîtes de dialogue](../mfc/dialog-data-exchange.md)  
  
4.  Cliquez sur **OK** pour revenir à l'Éditeur de boîtes de dialogue.  
  
    > [!TIP]
    >  Pour passer d'un contrôle de boîte de dialogue à son gestionnaire existant, double\-cliquez sur le contrôle.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Vous pouvez également utiliser l'onglet **Variables membres** dans l'**Assistant Classe MFC** afin d'ajouter de nouvelles variables membres pour une classe spécifique, et afficher celles qui ont déjà été définies.  
  
 Spécifications  
  
 MFC  
  
## Voir aussi  
 [Mappage de messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Classe MFC \(Assistant\)](../mfc/reference/mfc-class-wizard.md)   
 [Ajout d'une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../mfc/reference/adding-an-mfc-message-handler.md)