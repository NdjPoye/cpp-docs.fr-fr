---
title: "Classe CMDIFrameWndEx | Microsoft Docs"
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
  - "CMDIFrameWndEx.AddDockSite"
  - "CMDIFrameWndEx"
  - "CMDIFrameWndEx::AddDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWndEx, classe"
ms.assetid: dbcafcb3-9a7a-4f11-9dfe-ba57565c81d0
caps.latest.revision: 42
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CMDIFrameWndEx
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Étend les fonctionnalités d' [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md), une fenêtre frame d'interface multidocument \(MDI\) windows.  
  
## Syntaxe  
  
```  
class CMDIFrameWndEx : public CMDIFrameWnd  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIFrameWndEx::ActiveItemRecalcLayout](../Topic/CMDIFrameWndEx::ActiveItemRecalcLayout.md)|Recalcule la disposition de l'élément actif.|  
|`CMDIFrameWndEx::AddDockSite`|Cette méthode n'est pas utilisée.|  
|[CMDIFrameWndEx::AddPane](../Topic/CMDIFrameWndEx::AddPane.md)|Enregistre un volet avec le gestionnaire d'ancrage.|  
|[CMDIFrameWndEx::AdjustClientArea](../Topic/CMDIFrameWndEx::AdjustClientArea.md)|Réduit la zone cliente pour permettre d'une bordure.|  
|[CMDIFrameWndEx::AdjustDockingLayout](../Topic/CMDIFrameWndEx::AdjustDockingLayout.md)|Recalcule la disposition de tous les volets ancrés.|  
|[CMDIFrameWndEx::AreMDITabs](../Topic/CMDIFrameWndEx::AreMDITabs.md)|Détermine si les onglets MDI comportent les ou la fonctionnalité de groupes tabulée par MDI est activée.|  
|[CMDIFrameWndEx::CanCovertControlBarToMDIChild](../Topic/CMDIFrameWndEx::CanCovertControlBarToMDIChild.md)|Appelé par l'infrastructure pour déterminer si la fenêtre frame peut convertir des volets d'ancrage aux documents avec onglet.|  
|[CMDIFrameWndEx::ControlBarToTabbedDocument](../Topic/CMDIFrameWndEx::ControlBarToTabbedDocument.md)|Convertit le volet d'ancrage spécifié à un document avec onglets.|  
|[CMDIFrameWndEx::CreateDocumentWindow](../Topic/CMDIFrameWndEx::CreateDocumentWindow.md)|Crée une fenêtre de document enfant.|  
|[CMDIFrameWndEx::CreateNewWindow](../Topic/CMDIFrameWndEx::CreateNewWindow.md)|Appelé par l'infrastructure pour créer une fenêtre.|  
|`CMDIFrameWndEx::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMDIFrameWndEx::DockPane](../Topic/CMDIFrameWndEx::DockPane.md)|Ancre le volet spécifié à la fenêtre frame.|  
|[CMDIFrameWndEx::DockPaneLeftOf](../Topic/CMDIFrameWndEx::DockPaneLeftOf.md)|S'ancre un volet gauche d'un autre volet.|  
|[CMDIFrameWndEx::EnableAutoHidePanes](../Topic/CMDIFrameWndEx::EnableAutoHidePanes.md)|Enables masquer automatiquement le mode pour les volets lorsqu'ils sont ancrés sur les côtés spécifiés de la fenêtre frame principale.|  
|[CMDIFrameWndEx::EnableDocking](../Topic/CMDIFrameWndEx::EnableDocking.md)|Active l'ancrage des volets qui appartiennent à la fenêtre frame MDI.|  
|[CMDIFrameWndEx::EnableFullScreenMainMenu](../Topic/CMDIFrameWndEx::EnableFullScreenMainMenu.md)|Affiche ou masque le menu principal en mode plein écran.|  
|[CMDIFrameWndEx::EnableFullScreenMode](../Topic/CMDIFrameWndEx::EnableFullScreenMode.md)|Active le mode plein écran de la fenêtre frame.|  
|[CMDIFrameWndEx::EnableLoadDockState](../Topic/CMDIFrameWndEx::EnableLoadDockState.md)|Active ou désactive le chargement de l'état d'ancrage.|  
|[CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md)|Active ou désactive la fonctionnalité de groupes tabulée par MDI.|  
|[CMDIFrameWndEx::EnableMDITabs](../Topic/CMDIFrameWndEx::EnableMDITabs.md)|Active ou désactive la fonctionnalité d'onglets MDI.  Une fois activé, la fenêtre frame affiche un onglet pour chaque fenêtre enfant MDI.|  
|[CMDIFrameWndEx::EnableMDITabsLastActiveActivation](../Topic/CMDIFrameWndEx::EnableMDITabsLastActiveActivation.md)|Spécifie si le dernier onglet actif doit être lancé lorsque l'utilisateur ferme l'onglet actuel.|  
|[CMDIFrameWndEx::EnablePaneMenu](../Topic/CMDIFrameWndEx::EnablePaneMenu.md)|Active ou désactive la création automatique et la gestion du menu contextuel de volet, qui affiche une liste des volets de l'application.  .|  
|[CMDIFrameWndEx::EnableWindowsDialog](../Topic/CMDIFrameWndEx::EnableWindowsDialog.md)|Insère un élément de menu dont l'ID de commande appelle une boîte de dialogue d' [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) .|  
|[CMDIFrameWndEx::GetActivePopup](../Topic/CMDIFrameWndEx::GetActivePopup.md)|Retourne un pointeur vers le menu popup actuellement affiché.|  
|[CMDIFrameWndEx::GetPane](../Topic/CMDIFrameWndEx::GetPane.md)|Retourne un pointeur vers le volet ayant l'ID spécifiée de contrôle|  
|[CMDIFrameWndEx::GetDefaultResId](../Topic/CMDIFrameWndEx::GetDefaultResId.md)|Retourne l'ID des ressources partagées de la fenêtre frame MDI.|  
|[CMDIFrameWndEx::GetMDITabGroups](../Topic/CMDIFrameWndEx::GetMDITabGroups.md)|Retourne une liste MDI est tabulé windows.|  
|[CMDIFrameWndEx::GetMDITabs](../Topic/CMDIFrameWndEx::GetMDITabs.md)|Retourne une référence à la fenêtre avec tabulation soulignée.|  
|[CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems](../Topic/CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems.md)|Retourne une combinaison des balises qui détermine les éléments de menu contextuel sont valides lorsque la fonctionnalité de groupes tabulée par MDI est activée.|  
|[CMDIFrameWndEx::GetMenuBar](../Topic/CMDIFrameWndEx::GetMenuBar.md)|Retourne un pointeur vers un objet de barre de menus attaché à la fenêtre frame.|  
|[CMDIFrameWndEx::GetRibbonBar](../Topic/CMDIFrameWndEx::GetRibbonBar.md)|Récupère le contrôle de barre de ruban pour le frame.|  
|[CMDIFrameWndEx::GetTearOffBars](../Topic/CMDIFrameWndEx::GetTearOffBars.md)|Retourne une liste d' [CPane](../../mfc/reference/cpane-class.md)\- les objets dérivés qui sont dans un état d'arrachement.|  
|`CMDIFrameWndEx::GetThisClass`|Appelé par l'infrastructure pour obtenir un pointeur vers l'objet d' [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMDIFrameWndEx::GetToolbarButtonToolTipText](../Topic/CMDIFrameWndEx::GetToolbarButtonToolTipText.md)|Appelé par l'infrastructure lorsque l'application affiche l'info\-bulle d'un bouton de barre d'outils.|  
|[CMDIFrameWndEx::InsertPane](../Topic/CMDIFrameWndEx::InsertPane.md)|Stocke le volet spécifié par le gestionnaire d'ancrage.|  
|[CMDIFrameWndEx::IsFullScreen](../Topic/CMDIFrameWndEx::IsFullScreen.md)|Détermine si la fenêtre frame est en mode plein écran.|  
|[CMDIFrameWndEx::IsMDITabbedGroup](../Topic/CMDIFrameWndEx::IsMDITabbedGroup.md)|Détermine si MDI est tabulé des groupes que la fonctionnalité est activée.|  
|[CMDIFrameWndEx::IsMemberOfMDITabGroup](../Topic/CMDIFrameWndEx::IsMemberOfMDITabGroup.md)|Détermine si la fenêtre avec tabulation est spécifiée dans la liste de fenêtres qui sont dans MDI est tabulé des groupes.|  
|[CMDIFrameWndEx::IsMenuBarAvailable](../Topic/CMDIFrameWndEx::IsMenuBarAvailable.md)|Détermine si la fenêtre frame a une barre de menus.|  
|[CMDIFrameWndEx::IsPointNearDockSite](../Topic/CMDIFrameWndEx::IsPointNearDockSite.md)|Détermine si un point spécifié est vers le site d'ancrage.|  
|[CMDIFrameWndEx::IsPrintPreview](../Topic/CMDIFrameWndEx::IsPrintPreview.md)|Détermine si la fenêtre frame est en mode d'aperçu avant impression.|  
|[CMDIFrameWndEx::LoadFrame](../Topic/CMDIFrameWndEx::LoadFrame.md)|Crée une fenêtre frame des informations sur les ressources.  \(Substitutions `CMDIFrameWnd::LoadFrame`.\)|  
|[CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md)|Charge la mise en page spécifiée MDI est tabulé les groupes et la liste de documents précédemment ouverts.|  
|[CMDIFrameWndEx::MDITabMoveToNextGroup](../Topic/CMDIFrameWndEx::MDITabMoveToNextGroup.md)|Déplace l'onglet actif actuel \)de la fenêtre avec tabulation permet au suivant ou précédent groupe avec tabulation.|  
|[CMDIFrameWndEx::MDITabNewGroup](../Topic/CMDIFrameWndEx::MDITabNewGroup.md)|Crée un nouveau groupe avec tabulation qui a un guichet unique.|  
|[CMDIFrameWndEx::NegotiateBorderSpace](../Topic/CMDIFrameWndEx::NegotiateBorderSpace.md)|Négocie l'espace de bordure dans une fenêtre frame pendant OLE activation sur place.|  
|[CMDIFrameWndEx::OnCloseDockingPane](../Topic/CMDIFrameWndEx::OnCloseDockingPane.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton **Fermer** dans un volet ancrable.|  
|[CMDIFrameWndEx::OnCloseMiniFrame](../Topic/CMDIFrameWndEx::OnCloseMiniFrame.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton **Fermer** sur un mini fenêtre frame flottante.|  
|[CMDIFrameWndEx::OnClosePopupMenu](../Topic/CMDIFrameWndEx::OnClosePopupMenu.md)|Appelé par l'infrastructure lorsqu'un menu contextuel actif traite un message d' `WM_DESTROY` .|  
|[CMDIFrameWndEx::OnCmdMsg](../Topic/CMDIFrameWndEx::OnCmdMsg.md)|Appelé par l'infrastructure pour router et distribuer des messages de commande et mettre à jour les objets interface utilisateur de commande.|  
|[CMDIFrameWndEx::OnDrawMenuImage](../Topic/CMDIFrameWndEx::OnDrawMenuImage.md)|Appelé par l'infrastructure lorsque l'image associée à un élément de menu est dessinée.|  
|[CMDIFrameWndEx::OnDrawMenuLogo](../Topic/CMDIFrameWndEx::OnDrawMenuLogo.md)|Appelé par l'infrastructure lorsque [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)traite un message d' `WM_PAINT` .|  
|[CMDIFrameWndEx::OnEraseMDIClientBackground](../Topic/CMDIFrameWndEx::OnEraseMDIClientBackground.md)|Appelé par l'infrastructure lorsque la fenêtre frame MDI traite un message d' `WM_ERASEBKGND` .|  
|[CMDIFrameWndEx::OnMenuButtonToolHitTest](../Topic/CMDIFrameWndEx::OnMenuButtonToolHitTest.md)|Appelé par l'infrastructure lorsqu'un objet d' [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)traite un message d' `WM_NCHITTEST` .|  
|[CMDIFrameWndEx::OnMoveMiniFrame](../Topic/CMDIFrameWndEx::OnMoveMiniFrame.md)|Appelé par l'infrastructure pour déplacer une fenêtre mini\-frame.|  
|[CMDIFrameWndEx::OnSetPreviewMode](../Topic/CMDIFrameWndEx::OnSetPreviewMode.md)|Définit le mode aperçu avant impression de la fenêtre frame principale de l'application.  \(Substitutions [CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md).\)|  
|[CMDIFrameWndEx::OnShowCustomizePane](../Topic/CMDIFrameWndEx::OnShowCustomizePane.md)|Appelé par l'infrastructure lorsqu'un rapide personnaliser le volet est activé.|  
|[CMDIFrameWndEx::OnShowMDITabContextMenu](../Topic/CMDIFrameWndEx::OnShowMDITabContextMenu.md)|Appelé par l'infrastructure lorsqu'un menu contextuel doit être affiché sur l'un des onglets.  \(Valide pour MDI est tabulé des groupes uniquement.\)|  
|[CMDIFrameWndEx::OnShowPanes](../Topic/CMDIFrameWndEx::OnShowPanes.md)|Appelé par l'infrastructure pour afficher ou masquer des volets.|  
|[CMDIFrameWndEx::OnShowPopupMenu](../Topic/CMDIFrameWndEx::OnShowPopupMenu.md)|Appelé par l'infrastructure lorsqu'un menu contextuel est activé.|  
|[CMDIFrameWndEx::OnSizeMDIClient](../Topic/CMDIFrameWndEx::OnSizeMDIClient.md)|Appelé par l'infrastructure lorsque la taille de la fenêtre MDI de client change.|  
|[CMDIFrameWndEx::OnTearOffMenu](../Topic/CMDIFrameWndEx::OnTearOffMenu.md)|Appelé par l'infrastructure lorsqu'un menu qui contient une barre d'arrachement est activé.|  
|[CMDIFrameWndEx::OnUpdateFrameMenu](../Topic/CMDIFrameWndEx::OnUpdateFrameMenu.md)|Appelé par l'infrastructure pour mettre à jour le menu de frame.  \(Substitutions `CMDIFrameWnd::OnUpdateFrameMenu`.\)|  
|[CMDIFrameWndEx::PaneFromPoint](../Topic/CMDIFrameWndEx::PaneFromPoint.md)|Retourne le volet d'ancrage qui contient le point spécifié.|  
|`CMDIFrameWndEx::PreTranslateMessage`|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour convertir des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows d' [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et d' [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions `CMDIFrameWnd::PreTranslateMessage`.\)|  
|[CMDIFrameWndEx::RecalcLayout](../Topic/CMDIFrameWndEx::RecalcLayout.md)|Appelé par l'infrastructure à recalculer la disposition de la fenêtre frame.  \(Substitutions [CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md).\)|  
|[CMDIFrameWndEx::RemovePaneFromDockManager](../Topic/CMDIFrameWndEx::RemovePaneFromDockManager.md)|Annule l'inscription d'un volet et le supprime le gestionnaire d'ancrage.|  
|[CMDIFrameWndEx::SaveMDIState](../Topic/CMDIFrameWndEx::SaveMDIState.md)|Stocke la disposition actuelle MDI est tabulé les groupes et la liste de documents précédemment ouverts.|  
|[CMDIFrameWndEx::SetPrintPreviewFrame](../Topic/CMDIFrameWndEx::SetPrintPreviewFrame.md)|Définit la fenêtre frame d'aperçu avant impression.|  
|[CMDIFrameWndEx::SetupToolbarMenu](../Topic/CMDIFrameWndEx::SetupToolbarMenu.md)|Modifie un objet barre d'outils en recherchant les éléments fictifs et en les remplaçant par des éléments définis par l'utilisateur spécifié.|  
|[CMDIFrameWndEx::ShowFullScreen](../Topic/CMDIFrameWndEx::ShowFullScreen.md)|Bascule le frame principal du mode normal en mode plein écran.|  
|[CMDIFrameWndEx::ShowPane](../Topic/CMDIFrameWndEx::ShowPane.md)|Affiche ou masque le volet spécifié.|  
|[CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)|Crée une zone d' [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) et l'ouvre.|  
|[CMDIFrameWndEx::TabbedDocumentToControlBar](../Topic/CMDIFrameWndEx::TabbedDocumentToControlBar.md)|Convertit le document avec onglets spécifié à un volet d'ancrage.|  
|[CMDIFrameWndEx::UpdateCaption](../Topic/CMDIFrameWndEx::UpdateCaption.md)|Appelé par l'infrastructure pour mettre à jour la légende du frame de fenêtre.|  
|[CMDIFrameWndEx::UpdateMDITabbedBarsIcons](../Topic/CMDIFrameWndEx::UpdateMDITabbedBarsIcons.md)|Définit l'icône pour chaque volet tabulé par MDI.|  
|[CMDIFrameWndEx::WinHelp](../Topic/CMDIFrameWndEx::WinHelp.md)|Appelé par l'infrastructure pour initier l'application de WinHelp ou l'aide de contexte.  \(Substitutions [CWnd::WinHelp](../Topic/CWnd::WinHelp.md).\)|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIFrameWndEx::m\_bCanCovertControlBarToMDIChild](../Topic/CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild.md)|Détermine si les volets d'ancrage peuvent être convertis à des fenêtres MDI enfants.|  
|[CMDIFrameWndEx::m\_bDisableSetRedraw](../Topic/CMDIFrameWndEx::m_bDisableSetRedraw.md)|Active ou désactive les redessinent l'optimisation des fenêtres MDI enfants.|  
  
## Notes  
 Pour tirer parti des fonctionnalités étendues de personnalisation de votre application MDI, dérivez la classe de fenêtre frame MDI de l'application d' `CMDIFrameWndEx` au lieu d' `CMDIFrameWnd`.  
  
## Exemple  
 L'exemple suivant dérive d'une classe d' `CMDIFrameWndEx`.  Cet extrait de code provient d' [Exemple DrawClient : MFC Ruban\- est basé sur l'application de dessin d'objets OLE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#1](../../mfc/reference/codesnippet/CPP/cmdiframewndex-class_1.h)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)  
  
 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)  
  
## Configuration requise  
 **En\-tête :** afxMDIFrameWndEx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md)   
 [Classe CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)