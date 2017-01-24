---
title: "Connecting a Pop-up Menu to Your Application | Microsoft Docs"
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
helpviewer_keywords: 
  - "pop-up menus, connecting to applications"
  - "context menus, connecting to applications"
  - "menus, pop-up"
  - "shortcut menus, connecting to applications"
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Connecting a Pop-up Menu to Your Application
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour connecter un menu contextuel à votre application  
  
1.  Ajoutez un gestionnaire de messages pour [WM\_CONTEXTMENU](_win32_WM_CONTEXTMENU) \(par exemple\).  Pour plus d'informations, voir [Mappage de messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
2.  Ajoutez le code suivant au gestionnaire de messages :  
  
    ```  
    CMenu menu;  
    VERIFY(menu.LoadMenu(IDR_MENU1));  
    CMenu* pPopup = menu.GetSubMenu(0);  
    ASSERT(pPopup != NULL);  
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());  
    ```  
  
    > [!NOTE]
    >  Le [CPoint](../atl-mfc-shared/reference/cpoint-class.md) **passé par le gestionnaire de messages est exprimé en coordonnées d'écran.**  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 MFC  
  
## Voir aussi  
 [Creating Pop\-up Menus](../windows/creating-pop-up-menus.md)   
 [Menu Editor](../mfc/menu-editor.md)   
 [Menus](_win32_Menus)