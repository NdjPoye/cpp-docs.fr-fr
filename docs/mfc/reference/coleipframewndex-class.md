---
title: "COleIPFrameWndEx Class | Microsoft Docs"
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
  - "COleIPFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWndEx class"
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleIPFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `COleIPFrameWndEx` implémente un conteneur OLE qui prend en charge MFC. Vous devez dériver la classe de fenêtres frames sur place pour votre application depuis la classe `COleIPFrameWndEx`, au lieu de la dériver de la classe [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md).  
  
## Syntaxe  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleIPFrameWndEx::AddDockSite](../Topic/COleIPFrameWndEx::AddDockSite.md)||  
|[COleIPFrameWndEx::AddPane](../Topic/COleIPFrameWndEx::AddPane.md)||  
|[COleIPFrameWndEx::AdjustDockingLayout](../Topic/COleIPFrameWndEx::AdjustDockingLayout.md)||  
|[COleIPFrameWndEx::DockPane](../Topic/COleIPFrameWndEx::DockPane.md)||  
|[COleIPFrameWndEx::DockPaneLeftOf](../Topic/COleIPFrameWndEx::DockPaneLeftOf.md)|Ancre un volet à gauche d’un autre volet.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](../Topic/COleIPFrameWndEx::EnableAutoHidePanes.md)||  
|[COleIPFrameWndEx::EnableDocking](../Topic/COleIPFrameWndEx::EnableDocking.md)||  
|[COleIPFrameWndEx::EnablePaneMenu](../Topic/COleIPFrameWndEx::EnablePaneMenu.md)||  
|[COleIPFrameWndEx::GetActivePopup](../Topic/COleIPFrameWndEx::GetActivePopup.md)|Retourne un pointeur vers le menu contextuel actuellement affiché.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](../Topic/COleIPFrameWndEx::GetContainerFrameWindow.md)||  
|[COleIPFrameWndEx::GetDefaultResId](../Topic/COleIPFrameWndEx::GetDefaultResId.md)|Retourne l’ID de ressource de la fenêtre frame que vous avez spécifié quand la fenêtre a été chargée.|  
|[COleIPFrameWndEx::GetDockFrame](../Topic/COleIPFrameWndEx::GetDockFrame.md)||  
|[COleIPFrameWndEx::GetDockingManager](../Topic/COleIPFrameWndEx::GetDockingManager.md)||  
|[COleIPFrameWndEx::GetMainFrame](../Topic/COleIPFrameWndEx::GetMainFrame.md)||  
|[COleIPFrameWndEx::GetMenuBar](../Topic/COleIPFrameWndEx::GetMenuBar.md)|Retourne un pointeur vers l’objet de barre de menu attaché à la fenêtre frame.|  
|[COleIPFrameWndEx::GetPane](../Topic/COleIPFrameWndEx::GetPane.md)||  
|[COleIPFrameWndEx::GetTearOffBars](../Topic/COleIPFrameWndEx::GetTearOffBars.md)|Retourne une liste d’objets de volet qui sont dans un état détachable.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](../Topic/COleIPFrameWndEx::GetToolbarButtonToolTipText.md)|Appelée par l’infrastructure avant l’affichage de l’info\-bulle pour un bouton.|  
|[COleIPFrameWndEx::InsertPane](../Topic/COleIPFrameWndEx::InsertPane.md)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](../Topic/COleIPFrameWndEx::IsMenuBarAvailable.md)|Détermine si le pointeur vers l’objet de barre de menu n’est pas `NULL`.|  
|[COleIPFrameWndEx::IsPointNearDockSite](../Topic/COleIPFrameWndEx::IsPointNearDockSite.md)||  
|[COleIPFrameWndEx::LoadFrame](../Topic/COleIPFrameWndEx::LoadFrame.md)|\(Substitue `COleIPFrameWnd::LoadFrame`.\)|  
|[COleIPFrameWndEx::OnCloseDockingPane](../Topic/COleIPFrameWndEx::OnCloseDockingPane.md)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](../Topic/COleIPFrameWndEx::OnCloseMiniFrame.md)||  
|[COleIPFrameWndEx::OnClosePopupMenu](../Topic/COleIPFrameWndEx::OnClosePopupMenu.md)|Appelée par l’infrastructure quand un menu contextuel actif traite un message WM\_DESTROY.|  
|[COleIPFrameWndEx::OnCmdMsg](../Topic/COleIPFrameWndEx::OnCmdMsg.md)|\(Substitue `CFrameWnd::OnCmdMsg`.\)|  
|[COleIPFrameWndEx::OnDrawMenuImage](../Topic/COleIPFrameWndEx::OnDrawMenuImage.md)|Appelée par l’infrastructure quand l’image associée à un élément de menu est dessinée.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](../Topic/COleIPFrameWndEx::OnDrawMenuLogo.md)|Appelée par l’infrastructure quand un objet [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) traite un message WM\_PAINT.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](../Topic/COleIPFrameWndEx::OnMenuButtonToolHitTest.md)|Appelée par l’infrastructure quand un objet [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) traite un message WM\_NCHITTEST.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](../Topic/COleIPFrameWndEx::OnMoveMiniFrame.md)||  
|[COleIPFrameWndEx::OnSetPreviewMode](../Topic/COleIPFrameWndEx::OnSetPreviewMode.md)|Appelez cette fonction membre pour définir la fenêtre frame principale de l’application dans et en dehors du mode Aperçu avant impression. \(Substitue [CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md).\)|  
|[COleIPFrameWndEx::OnShowCustomizePane](../Topic/COleIPFrameWndEx::OnShowCustomizePane.md)||  
|[COleIPFrameWndEx::OnShowPanes](../Topic/COleIPFrameWndEx::OnShowPanes.md)||  
|[COleIPFrameWndEx::OnShowPopupMenu](../Topic/COleIPFrameWndEx::OnShowPopupMenu.md)|Appelée par l’infrastructure quand un menu contextuel est activé.|  
|[COleIPFrameWndEx::OnTearOffMenu](../Topic/COleIPFrameWndEx::OnTearOffMenu.md)|Appelée par l’infrastructure quand un menu avec une barre détachable est activé.|  
|[COleIPFrameWndEx::PaneFromPoint](../Topic/COleIPFrameWndEx::PaneFromPoint.md)||  
|[COleIPFrameWndEx::PreTranslateMessage](../Topic/COleIPFrameWndEx::PreTranslateMessage.md)|\(Substitue `COleIPFrameWnd::PreTranslateMessage`.\)|  
|[COleIPFrameWndEx::RecalcLayout](../Topic/COleIPFrameWndEx::RecalcLayout.md)|\(Substitue `COleIPFrameWnd::RecalcLayout`.\)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](../Topic/COleIPFrameWndEx::RemovePaneFromDockManager.md)||  
|[COleIPFrameWndEx::SetDockState](../Topic/COleIPFrameWndEx::SetDockState.md)|Applique l’état d’ancrage spécifié aux volets qui appartiennent à la fenêtre frame.|  
|[COleIPFrameWndEx::SetupToolbarMenu](../Topic/COleIPFrameWndEx::SetupToolbarMenu.md)|Modifie un objet de barre d’outils en recherchant des objets factices et en les remplaçant par les éléments définis par l’utilisateur spécifiés.|  
|[COleIPFrameWndEx::ShowPane](../Topic/COleIPFrameWndEx::ShowPane.md)||  
|[COleIPFrameWndEx::WinHelp](../Topic/COleIPFrameWndEx::WinHelp.md)|Appelée par l’infrastructure pour lancer l’application WinHelp ou l’aide contextuelle.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleIPFrameWndEx::InitUserToobars](../Topic/COleIPFrameWndEx::InitUserToobars.md)|Indique à l’infrastructure d’initialiser une plage d’ID de contrôle qui sont affectés aux barres d’outils définies par l’utilisateur.|  
  
## Exemple  
 L’exemple suivant montre comment créer une sous\-classe d’une instance de la classe `COleIPFrameWndEx` et surcharger ses méthodes. L’exemple montre comment surcharger la méthode `OnDestory`, la méthode `RepositionFrame`, la méthode `RecalcLayout` et la méthode `CalcWindowRect`. Cet extrait de code fait partie de l’[exemple Word Pad](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#1](../../mfc/reference/codesnippet/CPP/coleipframewndex-class_1.cpp)]  
  
## Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## Configuration requise  
 **En\-tête :** afxoleipframewndex.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)