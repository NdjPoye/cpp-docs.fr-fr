---
title: "CMFCDragFrameImpl Class | Microsoft Docs"
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
  - "CMFCDragFrameImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDragFrameImpl class"
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDragFrameImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCDragFrameImpl` dessine un rectangle de glisser\-déplacer qui s'affiche lorsque l'utilisateur fait glisser un volet en mode standard d'ancrage.  
  
## Syntaxe  
  
```  
class CMFCDragFrameImpl  
```  
  
## Notes  
 Un objet de cette classe est incorporé dans chaque objet de [CPane Class](../../mfc/reference/cpane-class.md) .  Ainsi, chaque volet qui utilise la méthode d' `CanFloat` affiche un rectangle de glisser\-déplacer lorsque l'utilisateur fait glisser la.  
  
 Vous pouvez contrôler l'épaisseur du rectangle de glisser\-déplacer à l'aide de [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessFloat](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat.md) et de [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessDock](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock.md).  
  
## Hiérarchie d'héritage  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxdragframeimpl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessFloat](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat.md)   
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessDock](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock.md)