---
title: "Testing the ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls"
  - "DHTML controls, tester"
  - "contrôles HTML, tester"
  - "testing controls"
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Testing the ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fois que vous avez créé votre projet, vous pouvez générer et tester le contrôle d'exemple.  Avant que vous ne faire, utilisez l'Affichage de classes et l'explorateur de solutions pour tester le projet.  Les éléments de votre projet sont décrits plus en détail dans [Identifier les éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
#### Pour générer et tester le contrôle ATL DHTML  
  
1.  Générez le projet.  Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
2.  Lorsque la génération est terminée, ouvrez Test Container.  Consultez [propriétés et événements de test avec Test Container](../mfc/testing-properties-and-events-with-test-container.md) pour plus d'informations sur l'accès à l'outil Test Container.  
  
3.  Dans l'outil Test Container, dans le menu de **Modifier** , cliquez sur **Insert New Control**.  
  
4.  Dans la boîte de dialogue de **Insérer un contrôle** , sélectionnez votre contrôle de la zone de liste.  Souvenez \-vous, son nom est basé sur le nom court que vous avez indiqué dans l'Assistant Contrôle ATL.  Cliquez sur **OK**.  
  
5.  Examinez le contrôle.  Notez qu'il a une barre de défilement.  Utilisez les poignées du de commande pour redimensionner le contrôle pour activer la barre de défilement.  
  
6.  Testez les boutons du contrôle.  La couleur d'arrière\-plan des modifications à la couleur indiquée par le bouton.  
  
7.  Fermez Test Container.  
  
 Ensuite, essayez [modifier le contrôle DHTML](../atl/modifying-the-atl-dhtml-control.md).  
  
## Voir aussi  
 [Prise en charge pour un contrôle DHTML](../atl/atl-support-for-dhtml-controls.md)