---
title: "Editing Control Properties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], undoing changes"
  - "controls [C++], editing properties"
  - "dialog box controls, editing properties"
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Editing Control Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour modifier les propriétés d'un contrôle ou de contrôles  
  
1.  Dans la boîte de dialogue, sélectionnez le contrôle que vous souhaitez modifier.  
  
    > [!NOTE]
    >  Si vous sélectionnez plusieurs contrôles, seules les propriétés communes aux contrôles sélectionnés peuvent être modifiées.  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), modifiez les propriétés de votre contrôle.  
  
    > [!NOTE]
    >  Lorsque vous attribuez la valeur **True** à la propriété **Bitmap** d'un contrôle de bouton, de case d'option ou de case à cocher, le style BS\_BITMAP est implémenté pour votre contrôle.  Pour plus d'informations, consultez [Button Styles](../mfc/reference/button-styles.md).  Pour obtenir un exemple d'association d'une bitmap à un contrôle, consultez [CButton::SetBitmap](../Topic/CButton::SetBitmap.md).  Les bitmaps n'apparaissent pas sur votre contrôle pendant que vous êtes dans l'éditeur de ressources de boîtes de dialogue.  
  
### Pour annuler les modifications apportées aux propriétés d'un contrôle  
  
1.  Assurez\-vous que le contrôle a le focus dans l'Éditeur de boîtes de dialogue.  
  
2.  Cliquez sur **Annuler** dans le menu **Edition** \(si le focus n'est pas sur le contrôle, la commande **Annuler** n'est pas disponible\).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)