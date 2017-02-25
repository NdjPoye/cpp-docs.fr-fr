---
title: "Ajout d&#39;une page de propri&#233;t&#233;s ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, ajouter des pages de propriétés"
  - "controls [ATL], pages de propriétés"
  - "pages de propriétés, ajouter"
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Ajout d&#39;une page de propri&#233;t&#233;s ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour ajouter une page de propriétés ATL \(Active Template Library\) à votre projet, ce dernier doit avoir été créé en tant qu'application ATL ou MFC prenant en charge ATL.  Vous pouvez utiliser l'[Assistant Projet ATL](../../atl/reference/atl-project-wizard.md) pour créer une application ATL ou [ajouter un objet ATL à votre application MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) afin d'implémenter la prise en charge ATL pour une application MFC.  
  
 Si vous ajoutez une page de propriétés pour un contrôle, ce dernier doit prendre en charge l'interface [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md).  Par défaut, cette interface se trouve dans la liste de dérivation de la classe de votre contrôle si vous [créez un contrôle ATL](../../atl/reference/adding-an-atl-control.md) à l'aide de l'[Assistant Contrôle ATL](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Si la classe de votre contrôle ne contient pas [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) dans sa liste de dérivation, vous devez l'ajouter manuellement.  
  
### Pour ajouter une page de propriétés ATL à votre projet  
  
1.  Dans l'**Explorateur de solutions** ou dans l'[affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom du projet auquel vous souhaitez ajouter la page de propriétés ATL.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans le volet Modèles de la boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md), cliquez sur **Page de propriétés ATL**, puis sur **Ouvrir** pour afficher l'[Assistant Page de propriétés ATL](../../atl/reference/atl-property-page-wizard.md).  
  
 Lorsque vous créez une page de propriétés pour un contrôle, vous devez fournir l'entrée [PROP\_PAGE](../Topic/PROP_PAGE.md) dans le mappage de propriétés du contrôle.  
  
## Voir aussi  
 [Pages de propriétés](../../atl/atl-com-property-pages.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Example: Implementing a Property Page](../../atl/example-implementing-a-property-page.md)