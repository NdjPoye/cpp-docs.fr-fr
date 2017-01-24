---
title: "Toolbar Button Properties | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "size, toolbar buttons"
  - "toolbar buttons (in Toolbar editor), setting properties"
  - "Toolbar editor, toolbar button properties"
  - "status bars, active toolbar button text"
  - "command IDs, toolbar buttons"
  - "width, toolbar buttons"
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Toolbar Button Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les propriétés d'un bouton de barre d'outils sont :  
  
|Propriété|Description|  
|---------------|-----------------|  
|**ID**|Définit l'ID pour le bouton.  La liste déroulante fournit des noms d'**ID** courants.|  
|**Largeur**|Définit la largeur du bouton.  Valeur recommandée : 16 pixels.|  
|**Hauteur**|Définit la hauteur du bouton.  Notez que la hauteur d'un bouton change la hauteur de tous les boutons de la barre d'outils.  Valeur recommandée : 15 pixels.|  
|**Prompt**|Définit le message affiché dans la barre d'état.  L'ajout de \\n et d'un nom ajoute une info\-bulle à ce bouton de barre d'outils.  Pour plus d'informations, consultez [Création d'une info\-bulle pour un bouton de barre d'outils](../mfc/creating-a-tool-tip-for-a-toolbar-button.md).|  
  
 **Width** et **Height** s'appliquent à tous les boutons.  Une bitmap utilisée pour créer une barre d'outils a une largeur maximale de 2048.  Donc si vous affectez à la largeur du bouton la valeur 512, vous pouvez avoir uniquement quatre boutons et si vous affectez à la largeur la valeur 513, vous pouvez avoir uniquement trois boutons.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 MFC ou ATL  
  
## Voir aussi  
 [Changing the Properties of a Toolbar Button](../mfc/changing-the-properties-of-a-toolbar-button.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)