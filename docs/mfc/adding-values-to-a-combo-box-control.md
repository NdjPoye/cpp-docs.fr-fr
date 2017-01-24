---
title: "Adding Values to a Combo Box Control | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.combo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combo boxes [C++], Data property"
  - "controls [Visual Studio], testing values in combo boxes"
  - "combo boxes [C++], adding values"
  - "combo boxes [C++], previewing values"
  - "controls [C++], testing values in combo boxes"
  - "Data property"
  - "combo boxes [C++], testing values"
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Values to a Combo Box Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez ajouter des valeurs à un contrôle Combo Box tant que l'Éditeur de boîtes de dialogue est ouvert.  
  
> [!TIP]
>  Il est conseillé d'ajouter toutes les valeurs à la zone de liste déroulante *avant* de dimensionner la zone dans l'Éditeur de boîtes de dialogue ou le texte qui doit s'afficher dans le contrôle peut être tronqué.  
  
#### Pour entrer des valeurs dans un contrôle Combo Box  
  
1.  Sélectionnez le contrôle Combo Box en cliquant dessus.  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), affichez la propriété **Data**.  
  
    > [!NOTE]
    >  Si vous affichez les propriétés groupées par type, **Data** s'affiche dans les propriétés **Misc**.  
  
3.  Cliquez dans la zone de valeur pour la propriété **Data** et tapez vos valeurs de données, séparées par des points\-virgules.  
  
    > [!NOTE]
    >  N'insérez pas d'espace entre les valeurs car ils interfèrent avec le tri alphabétique dans la liste déroulante.  
  
4.  Cliquez sur **Entrée** lorsque vous avez terminé d'ajouter des valeurs.  
  
 Pour obtenir des informations sur l'agrandissement de la partie déroulante d'une zone de liste déroulante, consultez [Définition de la taille d'une zone de liste déroulante et de sa liste déroulante](../mfc/setting-the-size-of-the-combo-box-and-its-drop-down-list.md).  
  
> [!NOTE]
>  Vous ne pouvez pas ajouter de valeurs à des projets Win32 à l'aide de cette procédure \(la propriété **Data** est grisée pour les projets Win32\).  Dans la mesure où les projets Win32 n'ont pas de bibliothèques qui ajoutent cette fonctionnalité, vous devez ajouter par programme des valeurs à une zone de liste déroulante avec un projet Win32.  
  
#### Pour tester l'apparence des valeurs dans une zone de liste déroulante  
  
1.  Après avoir entré les valeurs dans la propriété **Data**, cliquez sur le bouton **Tester la boîte de dialogue** dans la [barre d'outils Éditeur de boîtes de dialogue](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
     Essayez de faire défiler l'intégralité de la liste de valeurs.  Les valeurs s'affichent exactement comme elles ont été tapées dans la propriété **Data** dans la fenêtre Propriétés.  L'orthographe et les majuscules ne sont pas testés.  
  
     Appuyez sur ÉCHAP pour retourner dans l'Éditeur de boîtes de dialogue.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Configuration requise  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)