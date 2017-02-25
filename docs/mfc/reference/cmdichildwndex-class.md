---
title: "Classe CMDIChildWndEx | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIChildWndEx"
  - "GetThisClass"
  - "CMDIChildWndEx::PreTranslateMessage"
  - "CMDIChildWndEx::ActivateFrame"
  - "CMDIChildWndEx.GetThisClass"
  - "CMDIChildWndEx::AddDockSite"
  - "CMDIChildWndEx.CreateObject"
  - "CMDIChildWndEx::CreateObject"
  - "CMDIChildWndEx.ActivateFrame"
  - "CMDIChildWndEx::GetThisClass"
  - "CMDIChildWndEx.PreTranslateMessage"
  - "PreTranslateMessage"
  - "ActivateFrame"
  - "CreateObject"
  - "CMDIChildWndEx.AddDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIChildWndEx, classe"
  - "ActivateFrame, méthode"
  - "PreTranslateMessage, méthode"
  - "GetThisClass, méthode"
  - "CreateObject, méthode"
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# Classe CMDIChildWndEx
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMDIChildWndEx` fournit les fonctionnalités d'une fenêtre enfant d'interface multidocument \(MDI\) windows.  Elle étend les fonctionnalités de [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md).  L'infrastructure requiert cette classe lorsqu'une application MDI utilise certaines classes MFC.  
  
## Syntaxe  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](../Topic/CMDIChildWndEx::ActivateTopLevelFrame.md)|Appelle en interne par l'infrastructure pour activer le frame de niveau supérieur lorsque l'application doit être lancée d'une barre des tâches tableau.|  
|`CMDIChildWndEx::AddDockSite`|Cette méthode n'est pas utilisée ou n'est pas implémentée.|  
|[CMDIChildWndEx::AddPane](../Topic/CMDIChildWndEx::AddPane.md)|Ajoute un volet.|  
|[CMDIChildWndEx::AddTabbedPane](../Topic/CMDIChildWndEx::AddTabbedPane.md)|Ajoute un volet avec tabulation.|  
|[CMDIChildWndEx::AdjustDockingLayout](../Topic/CMDIChildWndEx::AdjustDockingLayout.md)|Règle la disposition d'ancrage.|  
|[CMDIChildWndEx::CanShowOnMDITabs](../Topic/CMDIChildWndEx::CanShowOnMDITabs.md)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](../Topic/CMDIChildWndEx::CanShowOnTaskBarTabs.md)|Indique l'infrastructure si l'enfant MDI peut être affiché sur les onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::CanShowOnWindowsList](../Topic/CMDIChildWndEx::CanShowOnWindowsList.md)|Retourne `TRUE` si le nom de fenêtre enfant MDI peut être affiché dans la boîte de dialogue de [CMFCWindowsManagerDialog Class](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) .  Sinon, retourne `FALSE`.|  
|`CMDIChildWndEx::CreateObject`|Appelé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMDIChildWndEx::DockPane](../Topic/CMDIChildWndEx::DockPane.md)|Ancre un volet.|  
|[CMDIChildWndEx::DockPaneLeftOf](../Topic/CMDIChildWndEx::DockPaneLeftOf.md)|S'ancre un volet gauche d'un autre volet.|  
|[CMDIChildWndEx::EnableAutoHidePanes](../Topic/CMDIChildWndEx::EnableAutoHidePanes.md)|Enables masquer automatiquement le mode pour les volets lorsqu'elles sont ancrées sur les côtés spécifiés dans la fenêtre.|  
|[CMDIChildWndEx::EnableDocking](../Topic/CMDIChildWndEx::EnableDocking.md)|Active l'ancrage de la fenêtre enfant au frame principal.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::EnableTaskbarThumbnailClipRect.md)|Active ou désactive à la sélection automatique d'une partie de la zone cliente d'une fenêtre d'affichage en tant que miniature de cette fenêtre dans la barre des tâches.|  
|[CMDIChildWndEx::GetDockingManager](../Topic/CMDIChildWndEx::GetDockingManager.md)||  
|[CMDIChildWndEx::GetDocumentName](../Topic/CMDIChildWndEx::GetDocumentName.md)|Retourne le nom du document qui s'affiche dans la fenêtre enfant MDI.|  
|[CMDIChildWndEx::GetFrameIcon](../Topic/CMDIChildWndEx::GetFrameIcon.md)|Appelé par l'infrastructure pour récupérer l'icône de fenêtre enfant MDI.|  
|[CMDIChildWndEx::GetFrameText](../Topic/CMDIChildWndEx::GetFrameText.md)|Appelé par l'infrastructure pour récupérer le texte de la fenêtre enfant MDI.|  
|[CMDIChildWndEx::GetPane](../Topic/CMDIChildWndEx::GetPane.md)|Recherche un volet spécifiée par l'ID de contrôle|  
|[CMDIChildWndEx::GetRelatedTabGroup](../Topic/CMDIChildWndEx::GetRelatedTabGroup.md)||  
|[CMDIChildWndEx::GetTabbedPane](../Topic/CMDIChildWndEx::GetTabbedPane.md)|Retourne un pointeur à un volet d'ancrage incorporé qui a été converti en un document avec onglets.|  
|[CMDIChildWndEx::GetTabProxyWnd](../Topic/CMDIChildWndEx::GetTabProxyWnd.md)|La fenêtre de proxy d'onglet de retour est stockée en fait avec les onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](../Topic/CMDIChildWndEx::GetTaskbarPreviewWnd.md)|Appelé par l'infrastructure lorsqu'il doit obtenir une fenêtre enfant \(généralement une vue ou une fenêtre fractionnée\) à afficher sur une miniature de l'onglet de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::GetTaskbarThumbnailClipRect.md)|Appelé par l'infrastructure lorsqu'il doit sélectionner une partie de la zone cliente d'une fenêtre pour afficher en tant que miniature de cette fenêtre dans la barre des tâches.|  
|`CMDIChildWndEx::GetThisClass`|Appelé par l'infrastructure pour obtenir un pointeur vers l'objet d' [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](../Topic/CMDIChildWndEx::GetToolbarButtonToolTipText.md)|Appelé par l'infrastructure pour récupérer une info\-bulle pour un bouton de barre d'outils.|  
|[CMDIChildWndEx::InsertPane](../Topic/CMDIChildWndEx::InsertPane.md)|Stocke le volet spécifié par le gestionnaire d'ancrage.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](../Topic/CMDIChildWndEx::InvalidateIconicBitmaps.md)|Invalide les performances bitmap iconique de l'enfant MDI.|  
|[CMDIChildWndEx::IsPointNearDockSite](../Topic/CMDIChildWndEx::IsPointNearDockSite.md)|Détermine si un point spécifié est vers le site d'ancrage.|  
|[CMDIChildWndEx::IsReadOnly](../Topic/CMDIChildWndEx::IsReadOnly.md)|Retourne `TRUE` si le document affiché dans la fenêtre enfant est en lecture seule.  Sinon, retourne `FALSE`.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](../Topic/CMDIChildWndEx::IsRegisteredWithTaskbarTabs.md)|Retourne RECTIFIENT si l'enfant MDI est correctement inscrit avec les onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::IsTabbedPane](../Topic/CMDIChildWndEx::IsTabbedPane.md)|Retourne `TRUE` si la fenêtre MDI enfant contient un volet d'ancrage.  Sinon, retourne `FALSE`.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](../Topic/CMDIChildWndEx::IsTaskbarTabsSupportEnabled.md)|Indique si l'enfant MDI peut apparaître sur des onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](../Topic/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled.md)|Indique si la sélection automatique d'une partie de la zone cliente d'une fenêtre à l'affichage en tant que miniature de cette fenêtre dans la barre des tâches est activée ou désactivée.|  
|[CMDIChildWndEx::m\_dwDefaultTaskbarTabPropertyFlags](../Topic/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags.md)|Une combinaison des balises, qui est passé par l'infrastructure à la méthode de SetTaskbarTabProperties, lorsqu'un onglet \(MDI enfants\) est stocké avec les onglets de la barre des tâches Windows 7.  La combinaison par défaut est STPF\_USEAPPTHUMBNAILWHENACTIVE &#124; STPF\_USEAPPPEEKWHENACTIVE.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](../Topic/CMDIChildWndEx::OnGetIconicLivePreviewBitmap.md)|Appelé par l'infrastructure lorsqu'il doit obtenir une bitmap pour l'aperçu actif de l'enfant MDI.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](../Topic/CMDIChildWndEx::OnGetIconicThumbnail.md)|Appelé par l'infrastructure lorsqu'il doit obtenir une bitmap pour la iconique miniature de l'enfant MDI.|  
|[CMDIChildWndEx::OnMoveMiniFrame](../Topic/CMDIChildWndEx::OnMoveMiniFrame.md)|Appelé par l'infrastructure pour déplacer une fenêtre mini\-frame.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](../Topic/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton.md)|Appelé par l'infrastructure lorsque l'utilisateur appuie sur le bouton Fermer sur la miniature de l'onglet de la barre des tâches.|  
|[CMDIChildWndEx::OnSetPreviewMode](../Topic/CMDIChildWndEx::OnSetPreviewMode.md)|Appelé par l'infrastructure permettant d'entrer ou annuler le mode aperçu avant impression.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailActivate.md)|Appelé par l'infrastructure lorsque la miniature de l'onglet de la barre des tâches doit traiter le message de WM\_ACTIVATE.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate.md)|Appelé par l'infrastructure lorsque la miniature de l'onglet de la barre des tâches doit traiter le message de WM\_MOUSEACTIVATE.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailStretch.md)|Appelé par l'infrastructure lorsqu'il doit étirer une bitmap pour l'aperçu miniature de l'onglet de la barre des tâches Windows 7 de l'enfant MDI.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](../Topic/CMDIChildWndEx::OnUpdateFrameTitle.md)|Appelé par l'infrastructure pour mettre à jour le titre de frame.  \(Substitutions `CMDIChildWnd::OnUpdateFrameTitle`.\)|  
|[CMDIChildWndEx::PaneFromPoint](../Topic/CMDIChildWndEx::PaneFromPoint.md)|Retourne le volet qui contient le point donné.|  
|`CMDIChildWndEx::PreTranslateMessage`|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour convertir des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows d' [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et d' [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMDIChildWndEx::RecalcLayout](../Topic/CMDIChildWndEx::RecalcLayout.md)|Recalcule la disposition de la fenêtre.|  
|[CMDIChildWndEx::RegisterTaskbarTab](../Topic/CMDIChildWndEx::RegisterTaskbarTab.md)|MDI enfants de registres avec les onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](../Topic/CMDIChildWndEx::RemovePaneFromDockManager.md)|Supprime un volet du gestionnaire d'ancrage.|  
|[CMDIChildWndEx::SetRelatedTabGroup](../Topic/CMDIChildWndEx::SetRelatedTabGroup.md)||  
|[CMDIChildWndEx::SetTaskbarTabActive](../Topic/CMDIChildWndEx::SetTaskbarTabActive.md)|Lance correspondre la barre des tâches tableau de Windows 7.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](../Topic/CMDIChildWndEx::SetTaskbarTabOrder.md)|MDI enfants des insertions avant fenêtre spécifiée sur les onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](../Topic/CMDIChildWndEx::SetTaskbarTabProperties.md)|Définit des propriétés d'une barre des tâches tableau de Windows 7.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::SetTaskbarThumbnailClipRect.md)|Appelle en interne par l'infrastructure pour définir le rectangle de découpage pour sélectionner une partie de la zone cliente d'une fenêtre pour afficher en tant que miniature de cette fenêtre dans la barre des tâches.|  
|[CMDIChildWndEx::ShowPane](../Topic/CMDIChildWndEx::ShowPane.md)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](../Topic/CMDIChildWndEx::UnregisterTaskbarTab.md)|Supprime l'enfant MDI des onglets de la barre des tâches Windows 7.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](../Topic/CMDIChildWndEx::UpdateTaskbarTabIcon.md)|Icône d'onglet de la barre des tâches Windows 7 de mises à jour.|  
  
## Notes  
 Pour tirer parti des fonctionnalités étendues d'ancrage dans les applications MDI, dérivez la classe de fenêtre enfant MDI de votre application pour `CMDIChildWndEx` au lieu d' [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## Exemple  
 L'exemple suivant dérive d'une classe d' `CMDIChildWndEx`.  Cet extrait de code provient d' [Exemple VisualStudioDemo : Application MFC Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/CPP/cmdichildwndex-class_1.h)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## Configuration requise  
 **En\-tête :** afxMDIChildWndEx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog Class](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)