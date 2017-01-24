---
title: "Viewing and Adding ActiveX Controls to a Dialog Box | Microsoft Docs"
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
  - "vc.controls.activex"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "dialog boxes [C++], adding ActiveX controls"
  - "Insert ActiveX Control command"
  - "ActiveX controls [C++], adding to dialog boxes"
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Viewing and Adding ActiveX Controls to a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avec Visual Studio, vous pouvez insérer des contrôles ActiveX dans votre boîte de dialogue.  
  
### Pour afficher les contrôles ActiveX disponibles  
  
1.  Ouvrez une boîte de dialogue dans l’Éditeur de boîtes de dialogue.  
  
2.  Cliquez avec le bouton droit n’importe où dans le corps de la boîte de dialogue.  
  
3.  Dans le menu contextuel, cliquez sur **Insérer un contrôle ActiveX**.  
  
     La boîte de dialogue [Insérer un contrôle ActiveX](../mfc/insert-activex-control-dialog-box.md) apparaît et affiche tous les contrôles ActiveX disponibles sur votre système. En bas de la boîte de dialogue figure le chemin d’accès au fichier de contrôle ActiveX.  
  
### Pour ajouter un contrôle ActiveX à une boîte de dialogue  
  
1.  Dans la boîte de dialogue [Insérer un contrôle ActiveX](../mfc/insert-activex-control-dialog-box.md), sélectionnez le contrôle que vous souhaitez ajouter à votre boîte de dialogue, puis cliquez sur **OK**.  
  
     Le contrôle apparaît dans la boîte de dialogue, où vous pouvez le modifier ou créer des gestionnaires comme vous le feriez pour n’importe quel autre contrôle.  
  
    > [!NOTE]
    >  Vous pouvez ajouter des contrôles ActiveX à la fenêtre [Boîte à outils](../Topic/Toolbox.md). Pour plus d’informations, consultez [Gestion des éléments et des onglets de la boîte à outils](http://msdn.microsoft.com/fr-fr/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
    > [!CAUTION]
    >  Il se peut que la distribution de tous les contrôles ActiveX sur votre système ne soit pas autorisée juridiquement. Reportez\-vous au contrat de licence du logiciel qui a installé les contrôles ou contactez l’éditeur du logiciel.  
  
     Vous pouvez placer des contrôles dans la fenêtre Boîte à outils pour en faciliter l’accès. Pour plus d’informations, consultez [Personnaliser la boîte de dialogue Boîte à outils](http://msdn.microsoft.com/fr-fr/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)