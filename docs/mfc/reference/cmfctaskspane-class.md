---
title: "CMFCTasksPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPane class"
ms.assetid: b456328e-2525-4642-b78b-9edd1a1a7d3f
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCTasksPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 La classe `CMFCTasksPane` implémente une liste d'éléments interactifs \(tâches\).  
  
## Syntaxe  
  
```  
class CMFCTasksPane : public CDockablePane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPane::CMFCTasksPane](../Topic/CMFCTasksPane::CMFCTasksPane.md)|Construit un objet `CMFCTasksPane`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPane::AddGroup](../Topic/CMFCTasksPane::AddGroup.md)|Ajoute un nouveau groupe de tâches au contrôle de volet des tâches.|  
|[CMFCTasksPane::AddLabel](../Topic/CMFCTasksPane::AddLabel.md)|Ajoute une nouvelle étiquette statique dans le groupe de tâches spécifié.|  
|[CMFCTasksPane::AddMRUFilesList](../Topic/CMFCTasksPane::AddMRUFilesList.md)|Ajoute les tâches spécifiées par une liste de fichiers utilisés récemment \(MRU\) dans un groupe.|  
|[CMFCTasksPane::AddPage](../Topic/CMFCTasksPane::AddPage.md)|Ajoute une nouvelle page au volet des tâches.|  
|[CMFCTasksPane::AddSeparator](../Topic/CMFCTasksPane::AddSeparator.md)||  
|[CMFCTasksPane::AddTask](../Topic/CMFCTasksPane::AddTask.md)|Ajoute une nouvelle tâche au groupe de tâches spécifié.|  
|[CMFCTasksPane::AddWindow](../Topic/CMFCTasksPane::AddWindow.md)|Ajoute une fenêtre enfant au volet des tâches.|  
|[CMFCTasksPane::CollapseAllGroups](../Topic/CMFCTasksPane::CollapseAllGroups.md)||  
|[CMFCTasksPane::CollapseGroup](../Topic/CMFCTasksPane::CollapseGroup.md)|Réduit un groupe par programmation.|  
|[CMFCTasksPane::CreateDefaultMiniframe](../Topic/CMFCTasksPane::CreateDefaultMiniframe.md)|\(Substitue [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md).\)|  
|[CMFCTasksPane::CreateMenu](../Topic/CMFCTasksPane::CreateMenu.md)|Appelé par l'infrastructure pour créer un menu pour le bouton de menu **Autres volets de tâches**.|  
|[CMFCTasksPane::EnableAnimation](../Topic/CMFCTasksPane::EnableAnimation.md)|Active ou désactive l'animation pendant la réduction ou le développement des groupes de tâches.|  
|[CMFCTasksPane::EnableGroupCollapse](../Topic/CMFCTasksPane::EnableGroupCollapse.md)|Spécifie si les groupes de tâches peuvent être réduits.|  
|[CMFCTasksPane::EnableHistoryMenuButtons](../Topic/CMFCTasksPane::EnableHistoryMenuButtons.md)|Active ou désactive les menus déroulants dans les boutons de navigation **Suivant** et **Précédent**.|  
|[CMFCTasksPane::EnableNavigationToolbar](../Topic/CMFCTasksPane::EnableNavigationToolbar.md)|Active ou désactive la barre d'outils de navigation.|  
|[CMFCTasksPane::EnableOffsetCustomControls](../Topic/CMFCTasksPane::EnableOffsetCustomControls.md)||  
|[CMFCTasksPane::EnableScrollButtons](../Topic/CMFCTasksPane::EnableScrollButtons.md)|Active les boutons de défilement à la place d'une barre de défilement.|  
|[CMFCTasksPane::EnableWrapLabels](../Topic/CMFCTasksPane::EnableWrapLabels.md)|Active ou désactive le retour automatique à la ligne pour les étiquettes.|  
|[CMFCTasksPane::EnableWrapTasks](../Topic/CMFCTasksPane::EnableWrapTasks.md)|Active ou désactive le retour automatique à la ligne pour les tâches.|  
|[CMFCTasksPane::GetActivePage](../Topic/CMFCTasksPane::GetActivePage.md)|Retourne l'index de base zéro pour la page active.|  
|[CMFCTasksPane::GetGroupCaptionHeight](../Topic/CMFCTasksPane::GetGroupCaptionHeight.md)|Retourne la hauteur des légendes de groupe.|  
|[CMFCTasksPane::GetGroupCaptionHorzOffset](../Topic/CMFCTasksPane::GetGroupCaptionHorzOffset.md)|Retourne le décalage actuel d'une légende de groupe par rapport aux bords gauche et droit du volet des tâches.|  
|[CMFCTasksPane::GetGroupCaptionVertOffset](../Topic/CMFCTasksPane::GetGroupCaptionVertOffset.md)|Retourne le décalage actuel d'une légende de groupe par rapport aux bords supérieur et inférieur du volet des tâches.|  
|[CMFCTasksPane::GetGroupCount](../Topic/CMFCTasksPane::GetGroupCount.md)|Retourne le nombre total de groupes.|  
|[CMFCTasksPane::GetGroupLocation](../Topic/CMFCTasksPane::GetGroupLocation.md)|Retourne l'index de groupe interne pour un groupe donné.|  
|[CMFCTasksPane::GetGroupVertOffset](../Topic/CMFCTasksPane::GetGroupVertOffset.md)|Retourne le décalage vertical d'un groupe.|  
|[CMFCTasksPane::GetHorzMargin](../Topic/CMFCTasksPane::GetHorzMargin.md)|Retourne l'espacement horizontal entre un volet de tâches et les bords de la zone cliente.|  
|[CMFCTasksPane::GetNextPages](../Topic/CMFCTasksPane::GetNextPages.md)||  
|[CMFCTasksPane::GetPageByGroup](../Topic/CMFCTasksPane::GetPageByGroup.md)|Récupère l'index de page pour un groupe spécifié.|  
|[CMFCTasksPane::GetPagesCount](../Topic/CMFCTasksPane::GetPagesCount.md)|Retourne le nombre de pages.|  
|[CMFCTasksPane::GetPreviousPages](../Topic/CMFCTasksPane::GetPreviousPages.md)||  
|[CMFCTasksPane::GetScrollBarCtrl](../Topic/CMFCTasksPane::GetScrollBarCtrl.md)|\(Substitue [CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md).\)|  
|[CMFCTasksPane::GetTask](../Topic/CMFCTasksPane::GetTask.md)|Récupère une tâche.|  
|[CMFCTasksPane::GetTaskCount](../Topic/CMFCTasksPane::GetTaskCount.md)|Retourne le nombre d'éléments de tâche d'un groupe spécifié.|  
|[CMFCTasksPane::GetTaskGroup](../Topic/CMFCTasksPane::GetTaskGroup.md)|Retourne un groupe de tâches pour un index de groupe donné.|  
|[CMFCTasksPane::GetTaskLocation](../Topic/CMFCTasksPane::GetTaskLocation.md)|Retourne le groupe et l'index pour une tâche donnée.|  
|[CMFCTasksPane::GetTasksHorzOffset](../Topic/CMFCTasksPane::GetTasksHorzOffset.md)|Retourne le décalage horizontal des tâches entre les bords gauche et droit de leurs groupes parents.|  
|[CMFCTasksPane::GetTasksIconHorzOffset](../Topic/CMFCTasksPane::GetTasksIconHorzOffset.md)||  
|[CMFCTasksPane::GetTasksIconVertOffset](../Topic/CMFCTasksPane::GetTasksIconVertOffset.md)||  
|[CMFCTasksPane::GetVertMargin](../Topic/CMFCTasksPane::GetVertMargin.md)|Retourne l'espacement vertical entre un volet de tâches et les bords de la zone cliente.|  
|[CMFCTasksPane::IsAccessibilityCompatible](../Topic/CMFCTasksPane::IsAccessibilityCompatible.md)|\(Substitue `CDockablePane::IsAccessibilityCompatible`.\)|  
|[CMFCTasksPane::IsAnimationEnabled](../Topic/CMFCTasksPane::IsAnimationEnabled.md)|Indique si l'animation est activée.|  
|[CMFCTasksPane::IsBackButtonEnabled](../Topic/CMFCTasksPane::IsBackButtonEnabled.md)|Indique si le bouton Précédent est activé.|  
|[CMFCTasksPane::IsForwardButtonEnabled](../Topic/CMFCTasksPane::IsForwardButtonEnabled.md)|Indique si le bouton Suivant est activé.|  
|[CMFCTasksPane::IsGroupCollapseEnabled](../Topic/CMFCTasksPane::IsGroupCollapseEnabled.md)||  
|[CMFCTasksPane::IsHistoryMenuButtonsEnabled](../Topic/CMFCTasksPane::IsHistoryMenuButtonsEnabled.md)|Indique si les boutons de navigation **Suivant** et **Précédent** ont des menus déroulants.|  
|[CMFCTasksPane::IsNavigationToolbarEnabled](../Topic/CMFCTasksPane::IsNavigationToolbarEnabled.md)|Indique si la barre d'outils de navigation est activée.|  
|[CMFCTasksPane::IsToolBox](../Topic/CMFCTasksPane::IsToolBox.md)||  
|[CMFCTasksPane::IsWrapLabelsEnabled](../Topic/CMFCTasksPane::IsWrapLabelsEnabled.md)|Indique si le volet des tâches effectue un retour automatique à la ligne dans les étiquettes.|  
|[CMFCTasksPane::IsWrapTasksEnabled](../Topic/CMFCTasksPane::IsWrapTasksEnabled.md)|Indique si le volet des tâches effectue un retour automatique à la ligne dans les tâches.|  
|[CMFCTasksPane::LoadState](../Topic/CMFCTasksPane::LoadState.md)|\(Substitue [CDockablePane::LoadState](http://msdn.microsoft.com/fr-fr/96110136-4f46-4764-8a76-3b4abaf77917).\)|  
|[CMFCTasksPane::OnCancel](../Topic/CMFCTasksPane::OnCancel.md)||  
|[CMFCTasksPane::OnClickTask](../Topic/CMFCTasksPane::OnClickTask.md)|Appelé par l'infrastructure quand l'utilisateur clique sur un élément dans le volet des tâches.|  
|[CMFCTasksPane::OnOK](../Topic/CMFCTasksPane::OnOK.md)||  
|[CMFCTasksPane::OnPressBackButton](../Topic/CMFCTasksPane::OnPressBackButton.md)|Appelé par l'infrastructure quand l'utilisateur clique sur le bouton Précédent.|  
|[CMFCTasksPane::OnPressForwardButton](../Topic/CMFCTasksPane::OnPressForwardButton.md)|Appelé par l'infrastructure quand l'utilisateur clique sur le bouton de navigation Suivant.|  
|[CMFCTasksPane::OnPressHomeButton](../Topic/CMFCTasksPane::OnPressHomeButton.md)|Appelé par l'infrastructure quand l'utilisateur clique sur le bouton de navigation Accueil.|  
|[CMFCTasksPane::OnPressOtherButton](../Topic/CMFCTasksPane::OnPressOtherButton.md)||  
|[CMFCTasksPane::OnSetAccData](../Topic/CMFCTasksPane::OnSetAccData.md)|\(Substitue [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCTasksPane::OnUpdateCmdUI](../Topic/CMFCTasksPane::OnUpdateCmdUI.md)|\(Substitue [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/fr-fr/5dd61606-1c12-40d4-b024-f3839aa5e2e0).\)|  
|[CMFCTasksPane::PreTranslateMessage](../Topic/CMFCTasksPane::PreTranslateMessage.md)|\(Substitue [CDockablePane::PreTranslateMessage](http://msdn.microsoft.com/fr-fr/49a242cc-b158-400e-9e01-0345ec9c3ffd).\)|  
|[CMFCTasksPane::RecalcLayout](../Topic/CMFCTasksPane::RecalcLayout.md)|\(Substitue [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CMFCTasksPane::RemoveAllGroups](../Topic/CMFCTasksPane::RemoveAllGroups.md)|Supprime tous les groupes sur la page spécifiée.|  
|[CMFCTasksPane::RemoveAllPages](../Topic/CMFCTasksPane::RemoveAllPages.md)|Supprime toutes les pages du volet des tâches à l'exception de la \(première\) page par défaut.|  
|[CMFCTasksPane::RemoveAllTasks](../Topic/CMFCTasksPane::RemoveAllTasks.md)|Supprime toutes les tâches du groupe.|  
|[CMFCTasksPane::RemoveGroup](../Topic/CMFCTasksPane::RemoveGroup.md)|Supprime un groupe.|  
|[CMFCTasksPane::RemovePage](../Topic/CMFCTasksPane::RemovePage.md)|Supprime une page spécifiée du volet des tâches.|  
|[CMFCTasksPane::RemoveTask](../Topic/CMFCTasksPane::RemoveTask.md)|Supprime une tâche d'un groupe de tâches.|  
|[CMFCTasksPane::SaveState](../Topic/CMFCTasksPane::SaveState.md)|\(Substitue [CDockablePane::SaveState](http://msdn.microsoft.com/fr-fr/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).\)|  
|[CMFCTasksPane::Serialize](../Topic/CMFCTasksPane::Serialize.md)|\(Substitue [CDockablePane::Serialize](http://msdn.microsoft.com/fr-fr/09787e59-e446-4e76-894b-206d303dcfd6).\)|  
|[CMFCTasksPane::SetActivePage](../Topic/CMFCTasksPane::SetActivePage.md)|Active une page spécifiée dans le volet des tâches.|  
|[CMFCTasksPane::SetCaption](../Topic/CMFCTasksPane::SetCaption.md)|Définit le nom de légende d'un volet de tâches.|  
|[CMFCTasksPane::SetGroupCaptionHeight](../Topic/CMFCTasksPane::SetGroupCaptionHeight.md)|Définit la hauteur d'une légende de groupe.|  
|[CMFCTasksPane::SetGroupCaptionHorzOffset](../Topic/CMFCTasksPane::SetGroupCaptionHorzOffset.md)|Définit le décalage horizontal d'une légende de groupe.|  
|[CMFCTasksPane::SetGroupCaptionVertOffset](../Topic/CMFCTasksPane::SetGroupCaptionVertOffset.md)|Définit le décalage vertical d'une légende de groupe.|  
|[CMFCTasksPane::SetGroupName](../Topic/CMFCTasksPane::SetGroupName.md)|Définit un nom de groupe.|  
|[CMFCTasksPane::SetGroupTextColor](../Topic/CMFCTasksPane::SetGroupTextColor.md)|Définit la couleur du texte d'une légende de groupe.|  
|[CMFCTasksPane::SetGroupVertOffset](../Topic/CMFCTasksPane::SetGroupVertOffset.md)|Définit le décalage vertical pour un groupe.|  
|[CMFCTasksPane::SetHorzMargin](../Topic/CMFCTasksPane::SetHorzMargin.md)|Définit l'espacement horizontal entre un volet de tâches et les bords de la zone cliente.|  
|[CMFCTasksPane::SetIconsList](../Topic/CMFCTasksPane::SetIconsList.md)|Définit la liste d'images associée aux tâches.|  
|[CMFCTasksPane::SetPageCaption](../Topic/CMFCTasksPane::SetPageCaption.md)|Définit le texte de légende d'une page de volet de tâches.|  
|[CMFCTasksPane::SetTaskName](../Topic/CMFCTasksPane::SetTaskName.md)|Définit le nom d'une tâche.|  
|[CMFCTasksPane::SetTasksIconHorzOffset](../Topic/CMFCTasksPane::SetTasksIconHorzOffset.md)||  
|[CMFCTasksPane::SetTasksIconVertOffset](../Topic/CMFCTasksPane::SetTasksIconVertOffset.md)||  
|[CMFCTasksPane::SetTaskTextColor](../Topic/CMFCTasksPane::SetTaskTextColor.md)|Définit la couleur du texte d'une tâche.|  
|[CMFCTasksPane::SetTasksHorzOffset](../Topic/CMFCTasksPane::SetTasksHorzOffset.md)|Définit le décalage horizontal des tâches entre les bords gauche et droit de leurs groupes parents.|  
|[CMFCTasksPane::SetVertMargin](../Topic/CMFCTasksPane::SetVertMargin.md)|Définit l'espacement vertical entre un volet de tâches et les bords de la zone cliente.|  
|[CMFCTasksPane::SetWindowHeight](../Topic/CMFCTasksPane::SetWindowHeight.md)|Définit la hauteur d'une fenêtre.|  
|[CMFCTasksPane::ShowCommandMessageString](../Topic/CMFCTasksPane::ShowCommandMessageString.md)||  
|[CMFCTasksPane::ShowTask](../Topic/CMFCTasksPane::ShowTask.md)|Affiche ou masque une tâche.|  
|[CMFCTasksPane::ShowTaskByCmdId](../Topic/CMFCTasksPane::ShowTaskByCmdId.md)|Affiche ou masque une tâche en fonction de son ID de commande.|  
|[CMFCTasksPane::Update](../Topic/CMFCTasksPane::Update.md)|Met à jour les éléments d'interface utilisateur graphique qui appartiennent à un volet de tâches.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPane::OnActivateTasksPanePage](../Topic/CMFCTasksPane::OnActivateTasksPanePage.md)|Appelé par l'infrastructure quand une nouvelle page de volet de tâches est activée.|  
  
## Notes  
 La classe `CMFCTasksPane` implémente les fonctionnalités suivantes :  
  
-   Les éléments peuvent être regroupés et chaque regroupement d'éléments peut être associé à une légende.  
  
-   Les regroupements d'éléments peuvent être réduits ou développés.  
  
-   Une icône peut être affectée à chaque élément du volet des tâches.  
  
-   Un élément individuel peut être associé à un ID de commande qui s'exécute quand un utilisateur clique sur l'élément.  Quand le clic se produit, le message `WM_COMMAND` est envoyé au propriétaire du contrôle de volet de tâches.  
  
 Pour utiliser le contrôle `CMFCTasksPane` dans votre application, procédez comme suit :  
  
1.  Incorporez un objet `CMFCTasksPane` dans la classe de fenêtre frame principale.  
  
2.  Pendant le traitement du message `WM_CREATE`, appelez la méthode `Create`.  Vous pouvez utiliser les styles [CControlBar](../../mfc/reference/ccontrolbar-class.md) normaux.  Pour plus d'informations, consultez `CControlBar::Create`.  
  
3.  Appelez la méthode [CMFCTasksPane::AddGroup](../Topic/CMFCTasksPane::AddGroup.md) pour ajouter différents groupes.  
  
4.  Appelez les fonctions membres [CMFCTasksPane::AddTask](../Topic/CMFCTasksPane::AddTask.md), [CMFCTasksPane::AddLabel](../Topic/CMFCTasksPane::AddLabel.md) ou [CMFCTasksPane::AddMRUFilesList](../Topic/CMFCTasksPane::AddMRUFilesList.md) pour ajouter de nouveaux éléments \(tâches\) à chaque groupe.  
  
5.  Appelez [CMFCTasksPane::EnableGroupCollapse](../Topic/CMFCTasksPane::EnableGroupCollapse.md) pour préciser si les groupes d'éléments peuvent être réduits.  
  
 L'illustration suivante représente un contrôle de volet de tâches standard.  Le premier groupe est un groupe *spécial* dont la légende est plus sombre.  Le troisième groupe est réduit.  Le dernier groupe est aligné au bas du volet des tâches et n'a pas de légende ; la dernière tâche du groupe est une simple étiquette :  
  
 ![Exemple du volet de tâches](../../mfc/reference/media/nexttaskpane.png "NextTaskPane")  
  
 Vous pouvez personnaliser l'apparence du volet des tâches en ajustant les marges et les décalages.  L'illustration suivante permet de mieux comprendre la fonction de ces variables :  
  
 ![Groupe de tâches personnalisées](../../mfc/reference/media/nexttaskgrpcustom.png "NextTaskGrpCustom")  
  
## Exemple  
 L'exemple suivant montre comment construire un objet `CMFCTasksPane` et utiliser différentes méthodes de la classe `CMFCTasksPane`.  L'exemple montre comment activer la réduction des groupes de tâches, activer les menus déroulants sur les boutons de navigation **Suivant** et **Précédent**, activer les boutons de défilement à la place d'une barre de défilement, activer le retour automatique à la ligne pour le texte des étiquettes, définir le nom de légende du volet des tâches, définir la couleur du texte d'une légende de groupe et définir les marges horizontales et verticales.  
  
 [!code-cpp[NVC_MFC_RibbonApp#28](../../mfc/reference/codesnippet/CPP/cmfctaskspane-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)  
  
## Configuration requise  
 **En\-tête :** afxTasksPane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)