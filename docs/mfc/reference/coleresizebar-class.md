---
title: "COleResizeBar Class | Microsoft Docs"
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
  - "COleResizeBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleResizeBar class"
  - "control bars, redimensionner"
  - "in-place items"
  - "in-place items, redimensionner"
  - "OLE items, redimensionner"
  - "resizing in-place OLE items"
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleResizeBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un type de barre de contrôles qui prend en charge le redimensionnement par OLE éléments sur place.  
  
## Syntaxe  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleResizeBar::COleResizeBar](../Topic/COleResizeBar::COleResizeBar.md)|Construit un objet `COleResizeBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleResizeBar::Create](../Topic/COleResizeBar::Create.md)|Crée et initialise une fenêtre enfant windows et l'associe à l'objet d' `COleResizeBar` .|  
  
## Notes  
 Les objets d'`COleResizeBar` apparaissent comme [CRectTracker](../../mfc/reference/crecttracker-class.md) avec les poignées de dimensionnement de bordure et externes hachées.  
  
 Les objets d'`COleResizeBar` sont généralement les membres incorporé des objets de fenêtre frame dérivés de la classe de [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) .  
  
 Pour plus d'informations, consultez l'article [lancement](../../mfc/activation-cpp.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC SUPERPAD](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)