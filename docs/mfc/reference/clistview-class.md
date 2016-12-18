---
title: "CListView Class | Microsoft Docs"
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
  - "CListView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListView class"
  - "vues, and common controls"
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CListView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Simplifie l'utilisation du contrôle de liste et de [CListCtrl](../../mfc/reference/clistctrl-class.md), la classe qui encapsule la fonctionnalité de contrôle liste, avec l'architecture Document\/Vue MFC.  
  
## Syntaxe  
  
```  
class CListView : public CCtrlView  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CListView::CListView](../Topic/CListView::CListView.md)|Construit un objet `CListView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CListView::GetListCtrl](../Topic/CListView::GetListCtrl.md)|Retourne le contrôle de liste associé à la vue.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CListView::RemoveImageList](../Topic/CListView::RemoveImageList.md)|Supprime la liste d'images spécifiée de la vue Liste.|  
  
## Notes  
 Pour plus d'informations sur cette architecture, consultez la vue d'ensemble de la classe de [CView](../../mfc/reference/cview-class.md) et les références croisées quotées trouve.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## Configuration requise  
 **Header:** afxcview.h  
  
## Voir aussi  
 [exemple MFC ROWLIST](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)