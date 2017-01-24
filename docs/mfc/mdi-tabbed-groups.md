---
title: "Groupes avec onglet MDI | Microsoft Docs"
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
  - "mdi, groupes avec onglet"
  - "groupes avec onglet"
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Groupes avec onglet MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fonctionnalité de groupes tabulée par l'interface à multiple documents \(MDI\) autorise les applications \(MDI\) à afficher une ou plusieurs fenêtres avec onglets \(ou groupes windows avec onglets, appelés *groupes à onglets*\) dans la zone client MDI.  Les fenêtres avec onglets peuvent être alignées verticalement ou horizontalement.  Si une application accueille plusieurs MDI groupe tabulé, les groupes sont séparés par des séparateurs.  
  
## Fonctionnalités  
 Les fonctionnalités des groupes tabulés MDI sont les suivantes :  
  
-   Une application peut créer des fenêtres avec onglets dynamiquement.  
  
-   Une application peut aligner les fenêtres avec onglets horizontalement ou verticalement.  
  
-   Les groupes de fenêtres avec onglets sont séparés par des séparateurs.  L'utilisateur peut redimensionner les groupes à onglets à l'aide du séparateur.  
  
-   L'utilisateur peut faire glisser des onglets entre les groupes.  
  
-   L'utilisateur peut faire glisser des onglets pour créer de nouveaux groupes.  
  
-   L'utilisateur peut déplacer des onglets ou créer des groupes à l'aide d'un menu contextuel.  
  
-   Une application peut enregistrer et charger la disposition des fenêtres avec onglets.  
  
-   Une application peut enregistrer et charger la liste des documents MDI.  
  
-   Une application peut accéder à des groupes à onglets et modifier leurs valeurs.  
  
### Utiliser les groupes tabulés MDI  
 Voici quelques tâches couramment réalisées à l'aide des groupes tabulés MDI :  
  
-   Pour activer les groupes tabulés MDI pour une fenêtre cadre principale, appelez [CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md).  Le deuxième paramètre de cette méthode est une instance de la classe `CMDITabInfo`.  Vous pouvez utiliser les paramètres par défaut ou les modifier avant d'appeler `CMDIFrameWndEx::EnableMDITabbedGroups`.  
  
-   Pour modifier les propriétés d'un groupe tabulé par MDI au moment de l'exécution, créer ou modifier un objet `CMDITabInfo` et appeler `CMDIFrameWndEx::EnableMDITabbedGroups` de nouveau  
  
-   Pour obtenir une liste des fenêtres tabulées MDI, appelez `CMDIFrameWndEx::GetMDITabGroups`.  
  
-   Pour créer un nouveau groupe tabulé MDI en regard d'un groupe avec onglet actif, appelez `CMDIFrameWndEx::MDITabNewGroup`.  
  
-   Pour déplacer le focus d'entrée à la fenêtre précédente ou suivante d'un groupe avec onglets, appelez `CMDIFrameWndEx::MDITabMoveToNextGroup`.  
  
-   Pour déterminer si une fenêtre est membre d'un appel de groupe tabulé par MDI `CMDIFrameWndEx::IsMemberOfMDITabGroup`.  
  
-   Pour déterminer si les onglets MDI ou groupes tabulés par MDI sont activés pour une fenêtre cadre principale, appelez `CMDIFrameWndEx::AreMDITabs`.  Pour déterminer si les groupes tabulés par MDI sont activés, appelez `CMDIFrameWndEx::IsMDITabbedGroup`.  
  
-   Pour afficher un menu contextuel lorsque l'utilisateur clique sur un onglet ou le fait glisser vers un autre groupe tabulé par MDI, remplacez `CMDIFrameWndEx::OnShowMDITabContextMenu` dans la classe dérivée `CMDIFrameWndEx`.  Si vous n'appliquez pas cette méthode, l'application n'affiche pas le menu contextuel.  
  
-   Pour enregistrer la mise en page des groupes tabulés par MDI dans une application, appelez `CMDIFrameWndEx::SaveMDIState`.  Pour charger un profil de groupe tabulé par MDI sauvegardé précédemment, appelez `CMDIFrameWndEx::LoadMDIState`.  Vous pouvez également appeler les méthodes suivantes pour charger ou enregistrer la liste des documents ouverts dans une application MDI.  Pour plus d'informations sur l'état MDI d'enregistrement et de chargement, consultez [CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md).  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)   
 [Classe CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md)   
 [Classe CMDIChildWndEx](../mfc/reference/cmdichildwndex-class.md)   
 [CMDITabInfo Class](../mfc/reference/cmditabinfo-class.md)