---
title: "Modification des styles de contr&#244;le de liste | Microsoft Docs"
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
  - "CListCtrl (classe), modifier les styles"
  - "CListCtrl (classe), styles"
  - "styles, CListCtrl"
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Modification des styles de contr&#244;le de liste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez modifier le style de la fenêtre d'un contrôle de liste \([CListCtrl](../mfc/reference/clistctrl-class.md)\) à tout moment après l'avoir créé.  Lorsque vous modifiez le style de la fenêtre, vous modifiez le type de vue que le contrôle utilise.  For example, to emulate the Explorer, you might supply menu items or toolbar buttons for switching the control between different views: icon view, list view, and so on.  
  
 For example, when the user selects your menu item, you could make a call to [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) to retrieve the current style of the control and then call [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) to reset the style.  Pour plus d'informations, consultez l'[Utilisation des contrôles list VIEW](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Les styles disponibles sont répertoriés dans [Créer](../Topic/CListCtrl::Create.md).  Les styles `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, et `LVS_REPORT` indiquent les quatre vues de contrôle de liste.  
  
## Styles étendus  
 Outre les styles standard pour un contrôle de liste, il existe un autre ensemble, appelés styles étendus.  Ces styles, décrits dans [Styles de Vue de Liste Etendus](http://msdn.microsoft.com/library/windows/desktop/bb774732) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], fournissent diverses fonctionnalités pratiques qui personnalisent de personnaliser le comportement de votre contrôle de liste.  Pour implémenter le comportement d'un certain style \(tel que la sélection de la souris\), effectuez un appel à [CListCtrl::SetExtendedStyle](../Topic/CListCtrl::SetExtendedStyle.md), en transmettant le style nécessaire.  L'exemple suivant illustre l'appel de la fonction :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/CPP/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  Pour que la sélection de la souris fonctionne, vous devez également créer **LVS\_EX\_ONECLICKACTIVATE** ou **LVS\_EX\_TWOCLICKACTIVATE** activés.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)