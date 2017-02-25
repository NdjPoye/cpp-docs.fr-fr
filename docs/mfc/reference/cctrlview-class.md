---
title: "CCtrlView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCtrlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCtrlView class"
  - "controls [MFC], common"
  - "vues, and common controls"
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CCtrlView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Adapte l'architecture Document\/Vue aux contrôles communs prennent en charge les versions 3,51 Windows 98 et Windows NT et versions ultérieures.  
  
## Syntaxe  
  
```  
class CCtrlView : public CView  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCtrlView::CCtrlView](../Topic/CCtrlView::CCtrlView.md)|Construit un objet `CCtrlView`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CCtrlView::OnDraw](../Topic/CCtrlView::OnDraw.md)|Appelé par l'infrastructure pour dessiner en utilisant le contexte spécifié de périphérique.|  
|[CCtrlView::PreCreateWindow](../Topic/CCtrlView::PreCreateWindow.md)|Appelé avant la création de la fenêtre de windows attachée à cet objet d' `CCtrlView` .|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CCtrlView::m\_dwDefaultStyle](../Topic/CCtrlView::m_dwDefaultStyle.md)|Contient le style par défaut pour la classe d'affichage.|  
|[CCtrlView::m\_strClass](../Topic/CCtrlView::m_strClass.md)|Contient le nom de classe de fenêtre pour la classe d'affichage.|  
  
## Notes  
 La classe `CCtrlView` et ses dérivés, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), et [CRichEditView](../../mfc/reference/cricheditview-class.md)correspondent, l'architecture Document\/Vue aux nouveaux contrôles communs prennent en charge les versions 3,51 Windows 95\/98 et Windows NT et versions ultérieures.  Pour plus d'informations sur l'architecture Document\/Vue, consultez l' [architecture Document\/Vue](../../mfc/document-view-architecture.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CView Class](../../mfc/reference/cview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CTreeView Class](../../mfc/reference/ctreeview-class.md)   
 [CListView Class](../../mfc/reference/clistview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)