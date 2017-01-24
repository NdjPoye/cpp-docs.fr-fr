---
title: "CPane Class | Microsoft Docs"
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
  - "CPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPane class"
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CPane` est une amélioration de [CControlBar Class](../../mfc/reference/ccontrolbar-class.md).  Si vous mettez à niveau un projet MFC existant, remplacez toutes les occurrences d' `CControlBar` par `CPane`.  
  
## Syntaxe  
  
```  
class CPane : public CBasePane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CPane::~CPane`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md)|Recalcule immédiatement la disposition d'un volet.|  
|[CPane::AllocElements](../Topic/CPane::AllocElements.md)|Alloue de la mémoire pour un usage interne.|  
|[CPane::AllowShowOnPaneMenu](../Topic/CPane::AllowShowOnPaneMenu.md)|Spécifie si le volet est répertorié dans la liste runtime\) générée de volets de l'application.|  
|[CPane::CalcAvailableSize](../Topic/CPane::CalcAvailableSize.md)|Calcule la différence en taille entre un rectangle spécifié et le rectangle actuel de la fenêtre.|  
|[CPane::CalcInsideRect](../Topic/CPane::CalcInsideRect.md)|Calcule le rectangle intérieur d'un volet, en fonction de les bordures et les préhenseurs.|  
|[CPane::CalcRecentDockedRect](../Topic/CPane::CalcRecentDockedRect.md)|Calcule le rectangle récemment ancré.|  
|[CPane::CalcSize](../Topic/CPane::CalcSize.md)|Calcule la taille du volet.|  
|[CPane::CanBeDocked](../Topic/CPane::CanBeDocked.md)|Détermine si le volet peut être ancré au volet de base spécifié.|  
|[CPane::CanBeTabbedDocument](../Topic/CPane::CanBeTabbedDocument.md)|Détermine si le volet peut être converti en un document avec onglets.|  
|[CPane::ConvertToTabbedDocument](../Topic/CPane::ConvertToTabbedDocument.md)|Convertit un volet ancrable à un document avec onglets.|  
|[CPane::CopyState](../Topic/CPane::CopyState.md)|Copie l'état d'un volet.  \(Substitutions [CBasePane::CopyState](../Topic/CBasePane::CopyState.md).\)|  
|[CPane::Create](../Topic/CPane::Create.md)|Crée une barre de contrôles et la attaché à l'objet d' `CPane` .|  
|[CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)|Crée une fenêtre mini\-frame pour un volet flottant.|  
|[CPane::CreateEx](../Topic/CPane::CreateEx.md)|Crée une barre de contrôles et la attaché à l'objet d' `CPane` .|  
|`CPane::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CPane::DockByMouse](../Topic/CPane::DockByMouse.md)|Ancre un volet à l'aide de la méthode d'ancrage de la souris.|  
|[CPane::DockPane](../Topic/CPane::DockPane.md)|Ancre le volet flottant à un volet de base.|  
|[CPane::DockPaneStandard](../Topic/CPane::DockPaneStandard.md)|Ancre un volet à l'aide de l'ancrage \(standard\) d'ensemble.|  
|[CPane::DockToFrameWindow](../Topic/CPane::DockToFrameWindow.md)|Ancre un volet ancrable à un frame.  \(Substitutions `CBasePane::DockToFrameWindow`.\)|  
|[CPane::DoesAllowSiblingBars](../Topic/CPane::DoesAllowSiblingBars.md)|Indique si vous pouvez ancrer un autre volet à la même ligne où le volet actif est ancré.|  
|[CPane::FloatPane](../Topic/CPane::FloatPane.md)|Flotte le volet.|  
|[CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md)|Retourne la quantité, en pixels, que le volet peut développer.|  
|[CPane::GetAvailableStretchSize](../Topic/CPane::GetAvailableStretchSize.md)|Retourne la quantité, en pixels, que le volet peut réduire.|  
|[CPane::GetBorders](../Topic/CPane::GetBorders.md)|Retourne la largeur des bordures du volet.|  
|[CPane::GetClientHotSpot](../Topic/CPane::GetClientHotSpot.md)|Retourne *la zone réactive* pour le volet.|  
|[CPane::GetDockSiteRow](../Topic/CPane::GetDockSiteRow.md)|Retourne la ligne d'ancrage dans laquelle le volet est ancré.|  
|[CPane::GetExclusiveRowMode](../Topic/CPane::GetExclusiveRowMode.md)|Détermine si le volet est en mode exclusif de ligne.|  
|[CPane::GetHotSpot](../Topic/CPane::GetHotSpot.md)|Retourne la zone réactive stockée dans un objet sous\-jacent d' `CMFCDragFrameImpl` .|  
|[CPane::GetMinSize](../Topic/CPane::GetMinSize.md)|Récupère le minimum autorisé la taille du volet.|  
|[CPane::GetPaneName](../Topic/CPane::GetPaneName.md)|Récupère le titre du volet.|  
|`CPane::GetResizeStep`|Utilisé en interne.|  
|`CPane::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CPane::GetVirtualRect](../Topic/CPane::GetVirtualRect.md)|Récupère *le rectangle virtuel* du volet.|  
|[CPane::IsChangeState](../Topic/CPane::IsChangeState.md)|Lorsque le volet est déplacé, cette méthode analyse la position du volet par rapport à d'autres volets, la dock des lignes, et la fenêtre mini\-frame, et retourne la valeur appropriée d' `AFX_CS_STATUS` .|  
|[CPane::IsDragMode](../Topic/CPane::IsDragMode.md)|Spécifie si le volet est déplacé.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](../Topic/CPane::IsInFloatingMultiPaneFrameWnd.md)|Spécifie si le volet est dans une fenêtre frame de plusieurs volet.  \(Substitutions `CBasePane::IsInFloatingMultiPaneFrameWnd`.\)|  
|[CPane::IsLeftOf](../Topic/CPane::IsLeftOf.md)|Détermine si le volet est laissé \(ou ci\-dessus\) du rectangle spécifié.|  
|[CPane::IsResizable](../Topic/CPane::IsResizable.md)|Détermine si le volet peut être redimensionné.  \(Substitutions [CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md).\)|  
|[CPane::IsTabbed](../Topic/CPane::IsTabbed.md)|Détermine si le volet a été inséré dans le contrôle onglet d'une fenêtre avec onglets.  \(Substitutions [CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md).\)|  
|[CPane::LoadState](../Topic/CPane::LoadState.md)|Charge l'état du volet du Registre.  \(Substitutions [CBasePane::LoadState](../Topic/CBasePane::LoadState.md).\)|  
|[CPane::MoveByAlignment](../Topic/CPane::MoveByAlignment.md)|Déplace le volet et le rectangle virtuel par la valeur spécifiée.|  
|[CPane::MovePane](../Topic/CPane::MovePane.md)|Déplace le volet au rectangle spécifié.|  
|[CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md)|Appelé par l'infrastructure lorsque le parent d'un volet a changé.|  
|[CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md)|Appelé par l'infrastructure lorsque le parent du volet est sur le point de modifier.|  
|[CPane::OnPressCloseButton](../Topic/CPane::OnPressCloseButton.md)|Appelé par l'infrastructure lorsque l'utilisateur choisit le bouton Fermer sur la légende pour le volet.|  
|`CPane::OnProcessDblClk`|Utilisé en interne.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|Appelé par l'infrastructure lorsqu'un menu spécial de volet est sur le point d'être affiché.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|Appelé par l'infrastructure lorsqu'un menu spécial de volet est sur le point d'être affiché.|  
|`CPane::PrepareToDock`|Utilisé en interne.|  
|[CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)|Recalcule les informations de disposition pour le volet.  \(Substitutions [CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md).\)|  
|[CPane::SaveState](../Topic/CPane::SaveState.md)|Enregistre l'état du volet au Registre.  \(Substitutions [CBasePane::SaveState](../Topic/CBasePane::SaveState.md).\)|  
|[CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md)|Signale un volet comme actif.|  
|[CPane::SetBorders](../Topic/CPane::SetBorders.md)|Définit les valeurs de bordure du volet.|  
|[CPane::SetClientHotSpot](../Topic/CPane::SetClientHotSpot.md)|Définit la zone réactive pour le volet.|  
|[CPane::SetDockState](../Topic/CPane::SetDockState.md)|Ancrage restaure les informations d'état du volet.|  
|[CPane::SetExclusiveRowMode](../Topic/CPane::SetExclusiveRowMode.md)|Active ou désactive le mode exclusif de ligne.|  
|[CPane::SetMiniFrameRTC](../Topic/CPane::SetMiniFrameRTC.md)|Définit les informations de classe d'exécution de la fenêtre mini\-frame par défaut.|  
|[CPane::SetMinSize](../Topic/CPane::SetMinSize.md)|Définit le minimum autorisé la taille du volet.|  
|[CPane::SetVirtualRect](../Topic/CPane::SetVirtualRect.md)|Définit *le rectangle virtuel* du volet.|  
|[CPane::StretchPaneDeferWndPos](../Topic/CPane::StretchPaneDeferWndPos.md)|Étire le volet verticalement ou horizontalement sur le style d'ancrage.|  
|[CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md)|Les bascule masquer automatiquement le mode.|  
|[CPane::UndockPane](../Topic/CPane::UndockPane.md)|Supprime le volet du site d'ancrage, du curseur par défaut, ou de la fenêtre mini\-frame où il est actuellement ancré.  \(Substitutions [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).\)|  
|[CPane::UpdateVirtualRect](../Topic/CPane::UpdateVirtualRect.md)|Met à jour le rectangle virtuel.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CPane::OnAfterDock](../Topic/CPane::OnAfterDock.md)|Appelé par l'infrastructure lorsqu'un volet était ancré.|  
|[CPane::OnAfterFloat](../Topic/CPane::OnAfterFloat.md)|Appelé par l'infrastructure lorsqu'un volet a été flotté.|  
|[CPane::OnBeforeDock](../Topic/CPane::OnBeforeDock.md)|Appelé par l'infrastructure lorsque le volet est sur le point d'être ancré.|  
|[CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md)|Appelé par l'infrastructure lorsqu'un volet est sur le point d'être flotté.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CPane::m\_bHandleMinSize](../Topic/CPane::m_bHandleMinSize.md)|Active la gestion cohérente de la taille minimale pour les volets.|  
|[CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md)|Contient des informations récentes d'ancrage.|  
  
## Notes  
 En général, les objets d' `CPane` ne sont pas instanciés directement.  Si vous avez besoin d'un volet qui possède des fonctionnalités d'ancrage, dérivez votre objet de [CDockablePane](../../mfc/reference/cdockablepane-class.md).  Si vous avez besoin de fonctionnalités de barre d'outils, dérivez votre objet de [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 Lorsque vous dérivez une classe d' `CPane`, il peut être ancré dans [CDockSite](../../mfc/reference/cdocksite-class.md) et il peut être flotté dans [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## Configuration requise  
 **en\-tête :** afxPane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)