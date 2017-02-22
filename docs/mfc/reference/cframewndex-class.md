---
title: "CFrameWndEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWndEx class"
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 41
---
# CFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'une interface monodocument fenêtre frame chevauchée ou instantanée de \(SDI\) windows, et fournit des membres pour gérer la fenêtre.  Elle étend la classe de [CFrameWnd](../../mfc/reference/cframewnd-class.md) .  
  
## Syntaxe  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](../Topic/CFrameWndEx::ActiveItemRecalcLayout.md)|Règle la disposition du élément OLE client et de la zone cliente du frame.|  
|`CFrameWndEx::AddDockSite`|Cette méthode n'est pas utilisée.|  
|[CFrameWndEx::AddPane](../Topic/CFrameWndEx::AddPane.md)|Enregistre une barre de contrôles avec le gestionnaire d'ancrage.|  
|[CFrameWndEx::AdjustDockingLayout](../Topic/CFrameWndEx::AdjustDockingLayout.md)|Recalcule la disposition de tous les volets qui sont ancrés à la fenêtre frame.|  
|[CFrameWndEx::DelayUpdateFrameMenu](../Topic/CFrameWndEx::DelayUpdateFrameMenu.md)|Définit le menu puis les mises à jour de frame il lorsque le traitement de commande est inactif.|  
|[CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md)|Ancre le volet spécifié à la fenêtre frame.|  
|[CFrameWndEx::DockPaneLeftOf](../Topic/CFrameWndEx::DockPaneLeftOf.md)|S'ancre un volet gauche d'un autre volet.|  
|[CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md)|Active le mode de masquer automatiquement pour les volets lorsqu'elles sont ancrées aux côtés spécifiés de la fenêtre frame principale.|  
|[CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md)|Active l'ancrage des volets qui appartiennent à la fenêtre frame.|  
|[CFrameWndEx::EnableFullScreenMainMenu](../Topic/CFrameWndEx::EnableFullScreenMainMenu.md)|Affiche ou masque le menu principal dans un mode plein écran.|  
|[CFrameWndEx::EnableFullScreenMode](../Topic/CFrameWndEx::EnableFullScreenMode.md)|Active le mode plein écran de la fenêtre frame.|  
|[CFrameWndEx::EnableLoadDockState](../Topic/CFrameWndEx::EnableLoadDockState.md)|Active ou désactive le chargement de l'état d'ancrage.|  
|[CFrameWndEx::EnablePaneMenu](../Topic/CFrameWndEx::EnablePaneMenu.md)|Active ou désactive la gestion automatique du menu de volet.|  
|[CFrameWndEx::GetActivePopup](../Topic/CFrameWndEx::GetActivePopup.md)|Retourne un pointeur vers le menu contextuel actuellement affiché.|  
|[CFrameWndEx::GetDefaultResId](../Topic/CFrameWndEx::GetDefaultResId.md)|Retourne l'ID de ressource que vous avez spécifié lorsque l'infrastructure a chargé la fenêtre frame.|  
|[CFrameWndEx::GetDockingManager](../Topic/CFrameWndEx::GetDockingManager.md)|Récupère l'objet de [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) de la fenêtre frame.|  
|[CFrameWndEx::GetMenuBar](../Topic/CFrameWndEx::GetMenuBar.md)|Retourne un pointeur vers l'objet de barre de menus attaché à la fenêtre frame.|  
|[CFrameWndEx::GetPane](../Topic/CFrameWndEx::GetPane.md)|Retourne un pointeur vers le volet ayant l'ID spécifiée|  
|[CFrameWndEx::GetRibbonBar](../Topic/CFrameWndEx::GetRibbonBar.md)|Récupère le contrôle de barre de ruban pour le frame.|  
|[CFrameWndEx::GetTearOffBars](../Topic/CFrameWndEx::GetTearOffBars.md)|Retourne une liste d'objets du volet qui sont dans un état d'arrachement.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](../Topic/CFrameWndEx::GetToolbarButtonToolTipText.md)|Appelé par l'infrastructure lorsque l'application affiche l'info\-bulle d'un bouton de barre d'outils.|  
|[CFrameWndEx::InsertPane](../Topic/CFrameWndEx::InsertPane.md)|Enregistre un volet avec le gestionnaire d'ancrage.|  
|[CFrameWndEx::IsFullScreen](../Topic/CFrameWndEx::IsFullScreen.md)|Détermine si la fenêtre frame est en mode plein écran.|  
|[CFrameWndEx::IsMenuBarAvailable](../Topic/CFrameWndEx::IsMenuBarAvailable.md)|Détermine si le pointeur à l'objet de barre de menus est valide.|  
|[CFrameWndEx::IsPointNearDockSite](../Topic/CFrameWndEx::IsPointNearDockSite.md)|Indique si le point se trouve dans une zone de la fenêtre contextuelle.|  
|[CFrameWndEx::IsPrintPreview](../Topic/CFrameWndEx::IsPrintPreview.md)|Indique si la fenêtre frame est en mode d'aperçu avant impression.|  
|[CFrameWndEx::LoadFrame](../Topic/CFrameWndEx::LoadFrame.md)|Cette méthode est appelée après construction pour créer la fenêtre frame et charger ses ressources.|  
|[CFrameWndEx::NegotiateBorderSpace](../Topic/CFrameWndEx::NegotiateBorderSpace.md)|Négociation OLE de bordure de client d'outils.|  
|[CFrameWndEx::OnActivate](../Topic/CFrameWndEx::OnActivate.md)|L'infrastructure appelle cette méthode lorsque l'entrée d'utilisateur est basculée ou quitte y retourne le frame.|  
|[CFrameWndEx::OnActivateApp](../Topic/CFrameWndEx::OnActivateApp.md)|Appelé par l'infrastructure lorsque l'application est activée ou désélectionnée.|  
|[CFrameWndEx::OnChangeVisualManager](../Topic/CFrameWndEx::OnChangeVisualManager.md)|Appelé par l'infrastructure lorsqu'une modification au frame requiert une modification au gestionnaire visuel.|  
|[CFrameWndEx::OnClose](../Topic/CFrameWndEx::OnClose.md)|l'infrastructure appelle cette méthode pour fermer le frame.|  
|[CFrameWndEx::OnCloseDockingPane](../Topic/CFrameWndEx::OnCloseDockingPane.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton **Fermer** dans un volet d'ancrage.|  
|[CFrameWndEx::OnCloseMiniFrame](../Topic/CFrameWndEx::OnCloseMiniFrame.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton **Fermer** sur un mini fenêtre frame flottante.|  
|[CFrameWndEx::OnClosePopupMenu](../Topic/CFrameWndEx::OnClosePopupMenu.md)|Appelé par l'infrastructure lorsqu'un menu contextuel actif traite un message de WM\_DESTROY.|  
|[CFrameWndEx::OnCmdMsg](../Topic/CFrameWndEx::OnCmdMsg.md)|Messages de commande des expéditions.|  
|[CFrameWndEx::OnContextHelp](../Topic/CFrameWndEx::OnContextHelp.md)|Appelé par l'infrastructure au contexte d'affichage associé l'aide.|  
|[CFrameWndEx::OnCreate](../Topic/CFrameWndEx::OnCreate.md)|Appelé par l'infrastructure après le frame est créé.|  
|[CFrameWndEx::OnDestroy](../Topic/CFrameWndEx::OnDestroy.md)|Appelé par l'infrastructure lorsque le frame est détruit.|  
|[CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md)|Appelé par l'infrastructure lorsque l'application dessine l'image associée à un élément de menu.|  
|[CFrameWndEx::OnDrawMenuLogo](../Topic/CFrameWndEx::OnDrawMenuLogo.md)|Appelé par l'infrastructure lorsqu'un objet d' `CMFCPopupMenu` traite un message de [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) .|  
|[CFrameWndEx::OnDWMCompositionChanged](../Topic/CFrameWndEx::OnDWMCompositionChanged.md)|Appelé par l'infrastructure lorsque la composition \(DWM\) du gestionnaire de fenêtrage a été activée ou désactivée.|  
|[CFrameWndEx::OnExitSizeMove](../Topic/CFrameWndEx::OnExitSizeMove.md)|Appelé par l'infrastructure lorsque le frame cesse de se déplacer ou redimensionner.|  
|[CFrameWndEx::OnGetMinMaxInfo](../Topic/CFrameWndEx::OnGetMinMaxInfo.md)|Appelé par l'infrastructure lorsque le frame est redimensionné pour définir des limites de dimension de fenêtre.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](../Topic/CFrameWndEx::OnIdleUpdateCmdUI.md)|Appelé par l'infrastructure pour mettre à jour l'affichage de frame lorsque le traitement de commande est inactif.|  
|[CFrameWndEx::OnLButtonDown](../Topic/CFrameWndEx::OnLButtonDown.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur appuie sur le bouton gauche de la souris.|  
|[CFrameWndEx::OnLButtonUp](../Topic/CFrameWndEx::OnLButtonUp.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur relâche le bouton gauche de la souris.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](../Topic/CFrameWndEx::OnMenuButtonToolHitTest.md)|Appelé par l'infrastructure lorsqu'un objet d' `CMFCToolBarButton` traite un message d' `WM_NCHITTEST` .|  
|[CFrameWndEx::OnMenuChar](../Topic/CFrameWndEx::OnMenuChar.md)|Appelé par l'infrastructure lorsqu'un menu est affiché et l'utilisateur appuie sur une touche qui ne correspond pas à une commande.|  
|[CFrameWndEx::OnMouseMove](../Topic/CFrameWndEx::OnMouseMove.md)|L'infrastructure appelle cette méthode lorsque le pointeur de l'se déplace.|  
|[CFrameWndEx::OnMoveMiniFrame](../Topic/CFrameWndEx::OnMoveMiniFrame.md)|Appelé par l'infrastructure lorsqu'une fenêtre de volet déplace.|  
|[CFrameWndEx::OnNcActivate](../Topic/CFrameWndEx::OnNcActivate.md)|Appelé par l'infrastructure lorsque la zone non cliente du cadre doit être redessinée pour indiquer une modification de l'état actif.|  
|[CFrameWndEx::OnNcCalcSize](../Topic/CFrameWndEx::OnNcCalcSize.md)|Appelé par l'infrastructure lorsque la taille et la position de la zone cliente doivent être calculées.|  
|[CFrameWndEx::OnNcHitTest](../Topic/CFrameWndEx::OnNcHitTest.md)|Appelé par l'infrastructure lorsque le pointeur de l'se déplace ou qu'un bouton de la souris est enfoncé ou libéré.|  
|[CFrameWndEx::OnNcMouseMove](../Topic/CFrameWndEx::OnNcMouseMove.md)|Appelé par l'infrastructure lorsque le pointeur de l'se déplace dans une zone non cliente.|  
|[CFrameWndEx::OnNcPaint](../Topic/CFrameWndEx::OnNcPaint.md)|Appelé par l'infrastructure lorsque la zone non cliente doit être peinte.|  
|[CFrameWndEx::OnPaneCheck](../Topic/CFrameWndEx::OnPaneCheck.md)|Appelé par l'infrastructure pour contrôler la visibilité d'un volet.|  
|[CFrameWndEx::OnPostPreviewFrame](../Topic/CFrameWndEx::OnPostPreviewFrame.md)|Appelé par l'infrastructure lorsque l'utilisateur a modifié l'état d'aperçu avant impression.|  
|[CFrameWndEx::OnPowerBroadcast](../Topic/CFrameWndEx::OnPowerBroadcast.md)|Appelé par l'infrastructure lorsqu'un événement puissant se produit.|  
|[CFrameWndEx::OnSetMenu](../Topic/CFrameWndEx::OnSetMenu.md)|Appelé par l'infrastructure pour remplacer le menu de fenêtre frame.|  
|[CFrameWndEx::OnSetPreviewMode](../Topic/CFrameWndEx::OnSetPreviewMode.md)|Appelé par l'infrastructure pour définir le mode d'aperçu avant impression pour le frame.|  
|[CFrameWndEx::OnSetText](../Topic/CFrameWndEx::OnSetText.md)|Appelé par l'infrastructure pour définir le texte d'une fenêtre.|  
|[CFrameWndEx::OnShowCustomizePane](../Topic/CFrameWndEx::OnShowCustomizePane.md)|Appelé par l'infrastructure lorsqu'un rapide personnaliser le volet est activé.|  
|[CFrameWndEx::OnShowPanes](../Topic/CFrameWndEx::OnShowPanes.md)|Appelé par l'infrastructure pour afficher ou masquer des volets.|  
|[CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md)|Appelé par l'infrastructure lorsqu'un menu contextuel est activé.|  
|[CFrameWndEx::OnSize](../Topic/CFrameWndEx::OnSize.md)|L'infrastructure appelle cette méthode lorsque la taille du frame de modification.|  
|[CFrameWndEx::OnSizing](../Topic/CFrameWndEx::OnSizing.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur redimensionne le frame.|  
|[CFrameWndEx::OnSysColorChange](../Topic/CFrameWndEx::OnSysColorChange.md)|Appelé par l'infrastructure lorsque les couleurs système sont modifiées.|  
|[CFrameWndEx::OnTearOffMenu](../Topic/CFrameWndEx::OnTearOffMenu.md)|Appelé par l'infrastructure lorsqu'un menu qui contient une barre d'arrachement est activé.|  
|[CFrameWndEx::OnToolbarContextMenu](../Topic/CFrameWndEx::OnToolbarContextMenu.md)|Appelé par l'infrastructure pour générer un menu contextuel de barre d'outils.|  
|[CFrameWndEx::OnToolbarCreateNew](../Topic/CFrameWndEx::OnToolbarCreateNew.md)|l'infrastructure appelle cette méthode pour créer une nouvelle barre d'outils.|  
|[CFrameWndEx::OnToolbarDelete](../Topic/CFrameWndEx::OnToolbarDelete.md)|Appelé par l'infrastructure lorsqu'une barre d'outils est désactivée.|  
|[CFrameWndEx::OnUpdateFrameMenu](../Topic/CFrameWndEx::OnUpdateFrameMenu.md)|Appelé par l'infrastructure pour définir le menu de frame.|  
|[CFrameWndEx::OnUpdateFrameTitle](../Topic/CFrameWndEx::OnUpdateFrameTitle.md)|l'infrastructure appelle cette méthode pour mettre à jour la barre de titre de la fenêtre frame.|  
|[CFrameWndEx::OnUpdatePaneMenu](../Topic/CFrameWndEx::OnUpdatePaneMenu.md)|Appelé par l'infrastructure pour mettre à jour le menu de volet.|  
|[CFrameWndEx::OnWindowPosChanged](../Topic/CFrameWndEx::OnWindowPosChanged.md)|Appelé par l'infrastructure lorsque le format d'image, la position, ou l'ordre de plan a changé en raison d'un appel à une méthode de gestion des fenêtres.|  
|[CFrameWndEx::PaneFromPoint](../Topic/CFrameWndEx::PaneFromPoint.md)|Retourne le volet d'ancrage qui contient le point spécifié.|  
|[CFrameWndEx::PreTranslateMessage](../Topic/CFrameWndEx::PreTranslateMessage.md)|Messages spécifiques de fenêtre de handles avant leur acheminées.|  
|[CFrameWndEx::RecalcLayout](../Topic/CFrameWndEx::RecalcLayout.md)|Règle la disposition du frame et de ses fenêtres enfants.|  
|[CFrameWndEx::RemovePaneFromDockManager](../Topic/CFrameWndEx::RemovePaneFromDockManager.md)|Annule l'inscription d'un volet et le supprimer de la liste interne dans le gestionnaire d'ancrage.|  
|[CFrameWndEx::SetDockState](../Topic/CFrameWndEx::SetDockState.md)|Restaure la disposition d'ancrage à l'état d'ancrage stocké dans le Registre.|  
|[CFrameWndEx::SetPrintPreviewFrame](../Topic/CFrameWndEx::SetPrintPreviewFrame.md)|Définit la fenêtre frame d'aperçu avant impression.|  
|[CFrameWndEx::SetupToolbarMenu](../Topic/CFrameWndEx::SetupToolbarMenu.md)|Insère des commandes définies par l'utilisateur dans un menu de la barre d'outils.|  
|[CFrameWndEx::ShowFullScreen](../Topic/CFrameWndEx::ShowFullScreen.md)|Bascule le frame principale entre les modes pleine page et normaux.|  
|[CFrameWndEx::ShowPane](../Topic/CFrameWndEx::ShowPane.md)|Affiche ou masque le volet spécifié.|  
|[CFrameWndEx::UpdateCaption](../Topic/CFrameWndEx::UpdateCaption.md)|Appelé par l'infrastructure pour mettre à jour la légende du frame de fenêtre.|  
|[CFrameWndEx::WinHelp](../Topic/CFrameWndEx::WinHelp.md)|Appelle l'application d' `WinHelp` ou l'aide associée par contexte.|  
  
## Exemple  
 L'exemple suivant montre comment hériter d'une classe de la classe d' `CFrameWndEx` .  l'exemple montre les signatures de méthode dans la sous\-classe, et comment substituer la méthode d' `OnShowPopupMenu` .  Cet extrait de code fait partie d' [Exemple de protection de Word](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/CPP/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/CPP/cframewndex-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## Configuration requise  
 **en\-tête :** afxframewndex.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)