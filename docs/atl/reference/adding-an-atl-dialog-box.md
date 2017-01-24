---
title: "Adding an ATL Dialog Box | Microsoft Docs"
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
  - "projets ATL, ajouter des ressources de boîtes de dialogue"
  - "boîtes de dialogue, ATL"
  - "boîtes de dialogue MFC, boîtes de dialogue ATL"
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding an ATL Dialog Box
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour ajouter une boîte de dialogue ATL à votre projet, votre projet doit être un projet ATL ou un projet MFC comprenant la prise en charge ATL.  Vous pouvez utiliser l'[Assistant Projet ATL](../../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou vous pouvez également [ajouter un objet ATL à votre application MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
 Par défaut, l'Assistant Dialogue ATL implémente une boîte de dialogue dérivée de [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md).  Cette classe comprend une prise en charge de l'hébergement des contrôles ActiveX et Windows.  Si vous ne souhaitez pas le temps système représenté par la prise en charge du contrôle ActiveX, une fois que l'Assistant a généré votre code, remplacez toutes les instances de `CAxDialogImpl` par [CSimpleDialog](../../atl/reference/csimpledialog-class.md) ou [CDialogImpl](../../atl/reference/cdialogimpl-class.md) comme classe de base.  
  
> [!NOTE]
>  `CSimpleDialog` crée uniquement des boîtes de dialogue modales qui prennent en charge uniquement des contrôles communs Windows.  `CDialogImpl` crée des zones de dialogue modales ou non modales.  
  
### Pour ajouter une ressource de dialogue ATL à votre projet  
  
1.  Créez un projet ATL en utilisant l'[Assistant Projet ATL](../../atl/reference/atl-project-wizard.md).  
  
2.  Dans [Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom du projet et cliquez sur **Ajouter** dans le menu contextuel.  Cliquez sur **Ajouter une classe**.  
  
3.  Dans le volet Modèles de la boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md), cliquez sur **Dialogue ATL**.  Cliquez sur **Ouvrir** pour afficher l'[Assistant Dialogue ATL](../../atl/reference/atl-dialog-wizard.md).  
  
 Pour plus d'informations, consultez [Implémentation d'une boîte de dialogue](../../atl/implementing-a-dialog-box.md).  
  
## Voir aussi  
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [classes de fenêtre](../../atl/atl-window-classes.md)   
 [Message Maps](../../atl/message-maps-atl.md)