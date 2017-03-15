---
title: "Switching Between Dialog Box Controls and Code | Microsoft Docs"
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
  - "events [C++], viewing for controls"
  - "Windows messages [C++], controls"
  - "messages [C++], viewing for dialog boxes"
  - "Dialog editor, accessing code"
  - "code [C++], switching from Dialog Editor"
  - "controls [C++], jumping to code"
  - "Dialog editor, switching between controls and code"
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Switching Between Dialog Box Controls and Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans les applications MFC, vous pouvez double\-cliquer sur les contrôles de boîte de dialogue pour afficher le code du gestionnaire ou pour créer rapidement des fonctions gestionnaires stub.  
  
 Lorsqu'un contrôle est sélectionné, cliquez sur le bouton **ControlEvents** ou le bouton **Messages** dans la [fenêtre Propriétés](../Topic/Properties%20Window.md) pour afficher une liste complète des messages et des événements Windows disponibles pour l'élément sélectionné.  Choisissez dans la liste pour créer ou modifier les fonctions gestionnaires.  
  
### Pour afficher le code à partir de l'Éditeur de boîtes de dialogue  
  
1.  Double\-cliquez sur un contrôle à l'intérieur de la boîte de dialogue pour passer à la déclaration de la fonction de gestion des messages implémentée en dernier.  \(Pour les classes de boîte de dialogue ATL, vous passez toujours à la définition du constructeur.\)  
  
### Pour afficher les événements pour un contrôle  
  
1.  Lorsqu'un contrôle est sélectionné, cliquez sur le bouton **ControlEvents** dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
    > [!NOTE]
    >  Si vous cliquez sur le bouton **ControlEvents** lorsque la *boîte de dialogue* a le focus, la liste de tous les contrôles de la boîte de dialogue est exposée, et vous pouvez la développer pour modifier les événements pour les contrôles individuels.  
  
     Lorsqu'un contrôle a le focus dans la boîte de dialogue, vous pouvez cliquer dessus avec le bouton droit, puis sélectionner **Ajouter un gestionnaire d'événements** dans le menu contextuel.  Cela vous permet de spécifier la classe à laquelle ce gestionnaire est ajouté.  Pour plus d'informations, consultez [Ajout d'un gestionnaire d'événements](../ide/adding-an-event-handler-visual-cpp.md).  
  
### Pour afficher des messages pour une boîte de dialogue  
  
1.  Lorsque la boîte de dialogue est sélectionnée, cliquez sur le bouton **Messages** dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Win32  
  
## Voir aussi  
 [Dialog Editor](../mfc/dialog-editor.md)