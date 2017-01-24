---
title: "Ajout d&#39;un objet simple ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.classes.adding.atl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, ajouter des objets"
  - "ATL, objets simples"
  - "objets (ATL)"
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;un objet simple ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour ajouter un objet ATL \(Active Template Library\) à votre projet, ce dernier doit avoir été créé en tant qu'application ATL ou MFC intégrant la prise en charge ATL.  Vous pouvez utiliser l'[Assistant Projet ATL](../../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou vous pouvez également [ajouter un objet ATL à votre application MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
 Vous pouvez définir des interfaces COM pour votre nouvel objet ATL lors de sa création ou les ajouter ultérieurement à l'aide de la commande [Implémenter l'interface](../../ide/implement-interface-wizard.md) du menu contextuel de l'affichage de classes.  
  
### Pour ajouter un objet simple ATL à votre projet COM ATL  
  
1.  Dans l'**Explorateur de solutions** ou dans l'[affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom du projet auquel vous souhaitez ajouter l'objet simple ATL.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans la boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md), dans le volet Modèles, cliquez sur **Objet simple ATL**, puis sur **Ouvrir** pour afficher l'[Assistant Objet simple ATL](../../atl/reference/atl-simple-object-wizard.md).  
  
4.  Définissez des options supplémentaires pour votre projet dans la page [Options](../../atl/reference/options-atl-simple-object-wizard.md) de l'Assistant Objet simple ATL.  
  
5.  Cliquez sur **Terminer** pour ajouter l'objet à votre projet.  
  
## Voir aussi  
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une nouvelle interface à un projet ATL](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)   
 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md)   
 [Ajout d'une méthode](../../ide/adding-a-method-visual-cpp.md)   
 [MFC, classe](../../mfc/reference/adding-an-mfc-class.md)   
 [Ajout d'une classe C\+\+ générique](../../ide/adding-a-generic-cpp-class.md)