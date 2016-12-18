---
title: "Ajout d&#39;un contr&#244;le ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, ajouter des contrôles"
  - "controls [ATL], ajouter aux projets"
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;un contr&#244;le ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour ajouter un objet d'interface utilisateur à un projet prenant en charge les interfaces de tous les conteneurs potentiels.  Pour prendre en charge ces interfaces, le projet doit avoir été créé en tant qu'application ATL ou MFC intégrant la prise en charge ATL.  Vous pouvez utiliser l'[Assistant Projet ATL](../../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou vous pouvez également [ajouter un objet ATL à votre application MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
### Pour ajouter un contrôle ATL à votre projet  
  
1.  Dans l'**Explorateur de solutions** ou dans l'[affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom du projet auquel vous souhaitez ajouter l'objet simple ATL.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans le volet Modèles de la boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md), cliquez sur **Contrôle ATL**, puis sur **Ajouter** pour afficher l'[Assistant Contrôle ATL](../../atl/reference/atl-control-wizard.md).  
  
 L'**Assistant Contrôle ATL** vous permet de créer l'un des trois types de contrôles suivants :  
  
-   Contrôle standard  
  
-   Contrôle composé  
  
-   Contrôle DHTML  
  
 En outre, vous pouvez réduire la taille du contrôle et supprimer les interfaces qui ne sont pas utilisées par la plupart des conteneurs en sélectionnant **Contrôle minimal** à la page **Options** de l'Assistant.  
  
## Voir aussi  
 [Adding Functionality to the Composite Control](../../atl/adding-functionality-to-the-composite-control.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATLFire Sample](http://msdn.microsoft.com/fr-fr/5b2649f1-f45b-4cfb-9c4b-4d9459c26b09)