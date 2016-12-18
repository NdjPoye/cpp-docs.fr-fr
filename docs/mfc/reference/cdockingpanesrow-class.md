---
title: "CDockingPanesRow Class | Microsoft Docs"
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
  - "CDockingPanesRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockingPanesRow class"
ms.assetid: e7a17832-0ebb-4bce-b799-cec9b60f76fe
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockingPanesRow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère une liste de volets qui se trouvent sur la même ligne horizontale ou verticale \(colonne\) d'un site d'ancrage.  
  
## Syntaxe  
  
```  
class CDockingPanesRow : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CDockingPanesRow::CDockingPanesRow`|Constructeur par défaut.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockingPanesRow::AddPane](../Topic/CDockingPanesRow::AddPane.md)||  
|[CDockingPanesRow::AddPaneFromRow](../Topic/CDockingPanesRow::AddPaneFromRow.md)||  
|[CDockingPanesRow::ArrangePanes](../Topic/CDockingPanesRow::ArrangePanes.md)|Dispose les volets dans une ligne en fonction des paramètres de marge et d'espacement spécifiés.|  
|[CDockingPanesRow::CalcFixedLayout](../Topic/CDockingPanesRow::CalcFixedLayout.md)||  
|[CDockingPanesRow::Create](../Topic/CDockingPanesRow::Create.md)||  
|[CDockingPanesRow::ExpandStretchedPanes](../Topic/CDockingPanesRow::ExpandStretchedPanes.md)||  
|[CDockingPanesRow::ExpandStretchedPanesRect](../Topic/CDockingPanesRow::ExpandStretchedPanesRect.md)||  
|[CDockingPanesRow::FixupVirtualRects](../Topic/CDockingPanesRow::FixupVirtualRects.md)||  
|[CDockingPanesRow::GetAvailableLength](../Topic/CDockingPanesRow::GetAvailableLength.md)||  
|[CDockingPanesRow::GetAvailableSpace](../Topic/CDockingPanesRow::GetAvailableSpace.md)||  
|[CDockingPanesRow::GetClientRect](../Topic/CDockingPanesRow::GetClientRect.md)||  
|[CDockingPanesRow::GetDockSite](../Topic/CDockingPanesRow::GetDockSite.md)||  
|[CDockingPanesRow::GetExtraSpace](../Topic/CDockingPanesRow::GetExtraSpace.md)||  
|[CDockingPanesRow::GetGroupFromPane](../Topic/CDockingPanesRow::GetGroupFromPane.md)||  
|[CDockingPanesRow::GetID](../Topic/CDockingPanesRow::GetID.md)||  
|[CDockingPanesRow::GetMaxPaneSize](../Topic/CDockingPanesRow::GetMaxPaneSize.md)||  
|[CDockingPanesRow::GetPaneCount](../Topic/CDockingPanesRow::GetPaneCount.md)||  
|[CDockingPanesRow::GetPaneList](../Topic/CDockingPanesRow::GetPaneList.md)||  
|[CDockingPanesRow::GetRowAlignment](../Topic/CDockingPanesRow::GetRowAlignment.md)||  
|[CDockingPanesRow::GetRowHeight](../Topic/CDockingPanesRow::GetRowHeight.md)||  
|[CDockingPanesRow::GetRowOffset](../Topic/CDockingPanesRow::GetRowOffset.md)||  
|[CDockingPanesRow::GetVisibleCount](../Topic/CDockingPanesRow::GetVisibleCount.md)||  
|[CDockingPanesRow::GetWindowRect](../Topic/CDockingPanesRow::GetWindowRect.md)||  
|[CDockingPanesRow::HasPane](../Topic/CDockingPanesRow::HasPane.md)||  
|[CDockingPanesRow::IsEmpty](../Topic/CDockingPanesRow::IsEmpty.md)||  
|[CDockingPanesRow::IsExclusiveRow](../Topic/CDockingPanesRow::IsExclusiveRow.md)||  
|[CDockingPanesRow::IsHorizontal](../Topic/CDockingPanesRow::IsHorizontal.md)||  
|[CDockingPanesRow::IsVisible](../Topic/CDockingPanesRow::IsVisible.md)||  
|[CDockingPanesRow::Move](../Topic/CDockingPanesRow::Move.md)||  
|[CDockingPanesRow::MovePane](../Topic/CDockingPanesRow::MovePane.md)||  
|[CDockingPanesRow::OnResizePane](../Topic/CDockingPanesRow::OnResizePane.md)||  
|[CDockingPanesRow::RedrawAll](../Topic/CDockingPanesRow::RedrawAll.md)||  
|[CDockingPanesRow::RemovePane](../Topic/CDockingPanesRow::RemovePane.md)||  
|[CDockingPanesRow::ReplacePane](../Topic/CDockingPanesRow::ReplacePane.md)||  
|[CDockingPanesRow::RepositionPanes](../Topic/CDockingPanesRow::RepositionPanes.md)||  
|[CDockingPanesRow::Resize](../Topic/CDockingPanesRow::Resize.md)||  
|[CDockingPanesRow::ResizeByPaneDivider](../Topic/CDockingPanesRow::ResizeByPaneDivider.md)||  
|[CDockingPanesRow::ScreenToClient](../Topic/CDockingPanesRow::ScreenToClient.md)||  
|[CDockingPanesRow::SetExtra](../Topic/CDockingPanesRow::SetExtra.md)||  
|[CDockingPanesRow::ShowDockSiteRow](../Topic/CDockingPanesRow::ShowDockSiteRow.md)||  
|[CDockingPanesRow::ShowPane](../Topic/CDockingPanesRow::ShowPane.md)||  
|[CDockingPanesRow::UpdateVisibleState](../Topic/CDockingPanesRow::UpdateVisibleState.md)||  
  
## Notes  
 Les objets `CDockingPanesRow` sont créés en interne par des objets de site d'ancrage.  
  
## Exemple  
 L'exemple suivant montre comment obtenir un objet `CDockingPanesRow` à partir d'un objet `CMFCAutoHideBar`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/CPP/cdockingpanesrow-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)  
  
## Configuration requise  
 **En\-tête :** afxDockingPanesRow.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)