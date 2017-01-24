---
title: "COleIPFrameWnd Class | Microsoft Docs"
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
  - "COleIPFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWnd class"
  - "in-place editing"
  - "OLE, modifier"
  - "OLE, in-place activation"
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleIPFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La base de la fenêtre de la modification sur place de votre application.  
  
## Syntaxe  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](../Topic/COleIPFrameWnd::COleIPFrameWnd.md)|Construit un objet `COleIPFrameWnd`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](../Topic/COleIPFrameWnd::OnCreateControlBars.md)|Appelé par l'infrastructure lorsqu'un élément est activé pour la modification sur place.|  
|[COleIPFrameWnd::RepositionFrame](../Topic/COleIPFrameWnd::RepositionFrame.md)|Appelé par l'infrastructure de repositionner la fenêtre d'édition visuelle.|  
  
## Notes  
 Cette classe crée et positionne les barres de contrôles dans la fenêtre de document de l'application conteneur.  Il gère également des notifications générées par un objet incorporé de [COleResizeBar](../../mfc/reference/coleresizebar-class.md) lorsque l'utilisateur redimensionne la fenêtre d'édition visuelle.  
  
 Pour plus d'informations sur l'utilisation `COleIPFrameWnd`, consultez l'article [lancement](../../mfc/activation-cpp.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)