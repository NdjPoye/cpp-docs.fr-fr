---
title: "Ajout d&#39;un gestionnaire d&#39;&#233;v&#233;nements (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.eventhandler.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestionnaires d'événements, ajouter"
  - "MSBuild, propriétés"
  - "propriétés (Visual Studio), MSBuild"
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;un gestionnaire d&#39;&#233;v&#233;nements (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'éditeur de ressources, vous pouvez ajouter un nouveau gestionnaire d'événements ou modifier un gestionnaire existant en recourant à l'[Assistant Gestionnaire d'événements](../ide/event-handler-wizard.md).  
  
 Vous pouvez ajouter un événement à la classe en implémentant la boîte de dialogue à l'aide de la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Si vous souhaitez ajouter l'événement à une classe autre que celle de la boîte de dialogue, utilisez l'Assistant Gestionnaire d'événements.  
  
### Pour ajouter un gestionnaire d'événements à un contrôle de boîte de dialogue  
  
1.  Double\-cliquez sur la ressource boîte de dialogue dans l'[Affichage des ressources](../windows/resource-view-window.md) pour ouvrir la ressource boîte de dialogue qui contient le contrôle dans l'[Éditeur de boîtes de dialogue](../mfc/dialog-editor.md).  
  
2.  Cliquez avec le bouton droit sur le contrôle pour lequel vous souhaitez gérer l'événement de notification.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter un gestionnaire d'événements** pour afficher l'Assistant Gestionnaire d'événements.  
  
4.  Dans la zone **Type de message**, sélectionnez l'événement à ajouter à la classe sélectionnée dans la zone **Liste de classes**.  
  
5.  Acceptez le nom par défaut de la zone **Nom du gestionnaire de fonctions** ou indiquez le nom de votre choix.  
  
6.  Cliquez sur **Ajouter** pour ajouter le gestionnaire d'événements au projet et ouvrez l'éditeur de texte à l'emplacement de la nouvelle fonction pour ajouter le code approprié du gestionnaire d'événements.  
  
     Si le type de message sélectionné possède déjà un gestionnaire d'événements pour la classe sélectionnée, **Ajouter** n'est pas disponible alors que **Modifier** l'est.  Cliquez sur **Modifier** pour ouvrir l'éditeur de texte à l'emplacement de la fonction existante.  
  
 Une autre solution consiste à ajouter les gestionnaires d'événements à partir de la [fenêtre Propriétés](../Topic/Properties%20Window.md).  Pour plus d'informations, consultez [Ajout de gestionnaires d'événements pour les contrôles de boîte de dialogue](../mfc/adding-event-handlers-for-dialog-box-controls.md).  
  
## Voir aussi  
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [Ajout d'une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)