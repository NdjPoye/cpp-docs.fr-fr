---
title: "Bo&#238;tes de dialogue | Microsoft Docs"
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
  - "CDialog (classe), boîtes de dialogue MFC"
  - "boîtes de dialogue MFC"
  - "MFC, boîtes de dialogue"
  - "boîtes de dialogue modales, boîtes de dialogue MFC"
  - "boîtes de dialogue non modales, boîtes de dialogue MFC"
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Bo&#238;tes de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications de Windows communiquent fréquemment par l'utilisateur via les boîtes de dialogue.  La classe [CDialog](../mfc/reference/cdialog-class.md) fournit une interface pour gérer les boîtes de dialogue, l'éditeur de boîtes de dialogue de Visual C\+\+ facilite ainsi la création de boîtes de dialogue et de création de ressources de modèles boîte de dialogue, les assistants de code simplifient le processus d'initialisation et de validation des contrôles dans une boîte de dialogue et pour rassembler les valeurs entrées par l'utilisateur.  
  
 Les boîtes de dialogue contiennent des contrôles, notamment :  
  
-   Les contrôles communs Windows tels que des zones d'édition, des boutons poussoir, des zones de liste, les zones de liste déroulante, les vérifications d'arborescence, des contrôles de liste, et les indicateurs de progression.  
  
-   Contrôles ActiveX  
  
-   Contrôles owner\-drawn : contrôles que vous êtes chargé de dessiner dans la boîte de dialogue.  
  
 La plupart des boîtes de dialogue sont modales, qui nécessitent l'utilisateur pour fermer la boîte de dialogue avant d'utiliser une autre partie du programme.  Mais il est possible de créer des boîtes de dialogue non modales, qui permettent aux utilisateurs d'utiliser d'autres fenêtres lorsque la boîte de dialogue est ouverte.  MFC prend en charge les deux types de boîte de dialogue avec la classe `CDialog`.  Les contrôles sont réorganisées et gérés en utilisant un modèle de la boîte de dialogue, créée avec [éditeur de boîtes de dialogue](../mfc/dialog-editor.md).  
  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md), également appelées boîtes de dialogue de l'onglet, sont des boîtes de dialogue qui contiennent des "pages" de contrôle distincts de la boîte de dialogue.  Chaque page contient le dossier « tab » onglet en haut.  Cliquez sur un onglet apporte cette page au début de la boîte de dialogue.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Exemple : affichage d'une boîte de dialogue via une commande de menu](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [Composants de boîte de dialogue dans le Framework](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [Boîtes de dialogue modales et non modales](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [Feuilles de propriétés et pages de propriétés](../mfc/property-sheets-and-property-pages-mfc.md) dans une boîte de dialogue  
  
-   [Création des ressources de boîte de dialogue](../mfc/creating-the-dialog-resource.md)  
  
-   [Création d'une classe de boîte de dialogue à l'aide de l'Assistant de Code](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [Échange \(DDX\) et validation \(DDV\) de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Accès de type sécurisé aux contrôles d'une boîte de dialogue](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [Mappage des messages Windows à votre classe](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [Fonctions membres couramment substituées](../mfc/commonly-overridden-member-functions.md)  
  
-   [Fonctions membres couramment ajoutées](../mfc/commonly-added-member-functions.md)  
  
-   [Classes de boîtes de dialogue communes](../mfc/common-dialog-classes.md)  
  
-   [Boîtes de dialogue dans OLE](../mfc/dialog-boxes-in-ole.md)  
  
-   Créé une application de l'interface utilisateur qui est une boîte de dialogue : consultez les exemples de programmation d'[CMNCTRL1](../top/visual-cpp-samples.md) ou d'[CMNCTRL2](../top/visual-cpp-samples.md).  Le créateur d'application fournit cette option.  
  
-   [Exemples](../mfc/dialog-sample-list.md)  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)