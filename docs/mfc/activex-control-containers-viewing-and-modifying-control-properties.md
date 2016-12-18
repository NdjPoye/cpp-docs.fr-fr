---
title: "Conteneurs de contr&#244;les ActiveX&#160;: consultation et modification des propri&#233;t&#233;s de contr&#244;le | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++), afficher et modifier des propriétés"
  - "contrôles ActiveX (C++), propriétés"
  - "contrôles (MFC), propriétés"
  - "propriétés (MFC), afficher et modifier"
  - "éditeurs de ressources, afficher et modifier des contrôles ActiveX"
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs de contr&#244;les ActiveX&#160;: consultation et modification des propri&#233;t&#233;s de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous insérez un contrôle ActiveX dans un projet, il est utile d'afficher et de modifier les propriétés prises en charge par le contrôle ActiveX.  Cet article explique comment utiliser l'éditeur de ressources Visual C\+\+ pour cela.  
  
 Si votre application au conteneur de contrôle ActiveX utilise les contrôles incorporés, vous pouvez afficher et modifier les propriétés du contrôle en restant dans l'éditeur de ressources.  Vous pouvez également utiliser l'éditeur de ressources pour définir les valeurs des propriétés au moment de la conception.  L'éditeur de ressources enregistre ensuite automatiquement ces valeurs dans le fichier de ressources du projet.  Une instance du contrôle sera ensuite les propriétés initialisées à ces valeurs.  
  
 Cette procédure suppose que vous avez inséré un contrôle dans votre projet.  Pour plus d'informations, consultez [Conteneurs de contrôle ActiveX : Insérer un contrôle dans une application de conteneur de contrôle](../mfc/inserting-a-control-into-a-control-container-application.md).  
  
 La première étape du visionnage des propriétés du contrôle est d'ajouter une instance du contrôle au modèle de boîte de dialogue du projet.  
  
### Pour voir les propriétés d'un contrôle utilisateur  
  
1.  Sous affichage des ressources, ouvrez le dossier **Boîte de dialogue**.  
  
2.  Ouvrez le modèle de la boîte de dialogue principal.  
  
3.  Insérez un contrôle ActiveX à l'aide de la boîte de dialogue **Insérer un contrôle ActiveX**.  Pour plus d'informations, consultez [Contrôles ActiveX de visualisation et d'ajout dans une boîte de dialogue](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
4.  Sélectionnez le contrôle ActiveX dans la boîte de dialogue.  
  
5.  Dans la fenêtre Propriétés, cliquez sur le bouton **Propriétés**.  
  
 Utilisez la boîte de dialogue **Propriétés** pour modifier et tester de nouvelles propriétés à la fois.  
  
## Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)