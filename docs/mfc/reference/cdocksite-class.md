---
title: "CDockSite Class | Microsoft Docs"
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
  - "CDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockSite class"
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 28
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Fournit les fonctionnalités de réorganisation des volets dérivés de la [CPane Class](../../mfc/reference/cpane-class.md) en ensembles de lignes.  
  
## Syntaxe  
  
```  
class CDockSite: public CBasePane  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockSite::AddRow](../Topic/CDockSite::AddRow.md)||  
|[CDockSite::AdjustDockingLayout](../Topic/CDockSite::AdjustDockingLayout.md)|\(Substitue [CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md).\)|  
|[CDockSite::AdjustLayout](../Topic/CDockSite::AdjustLayout.md)|\(Substitue [CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md).\)|  
|[CDockSite::AlignDockSite](../Topic/CDockSite::AlignDockSite.md)||  
|[CDockSite::CalcFixedLayout](../Topic/CDockSite::CalcFixedLayout.md)|\(Substitue [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CDockSite::CanAcceptPane](../Topic/CDockSite::CanAcceptPane.md)|\(Substitue [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md).\)|  
|[CDockSite::CreateEx](../Topic/CDockSite::CreateEx.md)|\(Substitue [CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md).\)|  
|[CDockSite::CreateRow](../Topic/CDockSite::CreateRow.md)||  
|[CDockSite::DockPane](../Topic/CDockSite::DockPane.md)|\(Substitue [CBasePane::DockPane](../Topic/CBasePane::DockPane.md).\)|  
|[CDockSite::DoesAllowDynInsertBefore](../Topic/CDockSite::DoesAllowDynInsertBefore.md)|\(Substitue [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CDockSite::FindRowIndex](../Topic/CDockSite::FindRowIndex.md)||  
|[CDockSite::FixupVirtualRects](../Topic/CDockSite::FixupVirtualRects.md)||  
|[CDockSite::GetDockSiteID](../Topic/CDockSite::GetDockSiteID.md)||  
|[CDockSite::GetDockSiteRowsList](../Topic/CDockSite::GetDockSiteRowsList.md)||  
|[CDockSite::IsAccessibilityCompatible](../Topic/CDockSite::IsAccessibilityCompatible.md)|\(Substitue `CBasePane::IsAccessibilityCompatible`.\)|  
|[CDockSite::IsDragMode](../Topic/CDockSite::IsDragMode.md)||  
|[CDockSite::IsLastRow](../Topic/CDockSite::IsLastRow.md)||  
|[CDockSite::IsRectWithinDockSite](../Topic/CDockSite::IsRectWithinDockSite.md)||  
|[CDockSite::IsResizable](../Topic/CDockSite::IsResizable.md)|\(Substitue [CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md).\)|  
|[CDockSite::MovePane](../Topic/CDockSite::MovePane.md)||  
|[CDockSite::OnInsertRow](../Topic/CDockSite::OnInsertRow.md)||  
|[CDockSite::OnRemoveRow](../Topic/CDockSite::OnRemoveRow.md)||  
|[CDockSite::OnResizeRow](../Topic/CDockSite::OnResizeRow.md)||  
|[CDockSite::OnSetWindowPos](../Topic/CDockSite::OnSetWindowPos.md)||  
|[CDockSite::OnShowRow](../Topic/CDockSite::OnShowRow.md)||  
|[CDockSite::OnSizeParent](../Topic/CDockSite::OnSizeParent.md)||  
|[CDockSite::PaneFromPoint](../Topic/CDockSite::PaneFromPoint.md)|Retourne un volet ancré dans le site d'ancrage au point spécifié par le paramètre donné.|  
|[CDockSite::DockPaneLeftOf](../Topic/CDockSite::DockPaneLeftOf.md)|Ancre un volet à gauche d'un autre volet.|  
|[CDockSite::FindPaneByID](../Topic/CDockSite::FindPaneByID.md)|Retourne le volet identifié par l'ID donné.|  
|[CDockSite::GetPaneList](../Topic/CDockSite::GetPaneList.md)|Retourne la liste des volets ancrés sur le site d'ancrage.|  
|[CDockSite::RectSideFromPoint](../Topic/CDockSite::RectSideFromPoint.md)||  
|[CDockSite::RemovePane](../Topic/CDockSite::RemovePane.md)||  
|[CDockSite::RemoveRow](../Topic/CDockSite::RemoveRow.md)||  
|[CDockSite::ReplacePane](../Topic/CDockSite::ReplacePane.md)||  
|[CDockSite::RepositionPanes](../Topic/CDockSite::RepositionPanes.md)||  
|[CDockSite::ResizeDockSite](../Topic/CDockSite::ResizeDockSite.md)||  
|[CDockSite::ResizeRow](../Topic/CDockSite::ResizeRow.md)||  
|[CDockSite::ShowPane](../Topic/CDockSite::ShowPane.md)|Affiche le volet.|  
|[CDockSite::ShowRow](../Topic/CDockSite::ShowRow.md)||  
|[CDockSite::SwapRows](../Topic/CDockSite::SwapRows.md)||  
  
## Notes  
 L'infrastructure crée automatiquement des objets `CDockSite` quand vous appelez [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md).  Les fenêtres du site d'ancrage sont positionnées à l'extrémité de la zone cliente de la fenêtre frame principale.  
  
 En général, il n'est pas utile d'appeler les services fournis par le site d'ancrage, car [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md) gère ces services.  
  
## Exemple  
 L'exemple suivant montre comment créer un objet de la classe `CDockSite`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/CPP/cdocksite-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## Configuration requise  
 **En\-tête :** afxDockSite.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)