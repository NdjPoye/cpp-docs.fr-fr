---
title: "CMiniFrameWnd Class | Microsoft Docs"
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
  - "CMiniFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMiniFrameWnd class"
  - "mini-frame windows"
  - "barres d'outils (C++)"
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMiniFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une fenêtre frame demi\-hauteur généralement vue autour de les barres d'outils flottante.  
  
## Syntaxe  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](../Topic/CMiniFrameWnd::CMiniFrameWnd.md)|Construit un objet `CMiniFrameWnd`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMiniFrameWnd::Create](../Topic/CMiniFrameWnd::Create.md)|Crée un objet d' `CMiniFrameWnd` après construction.|  
|[CMiniFrameWnd::CreateEx](../Topic/CMiniFrameWnd::CreateEx.md)|Crée un objet d' `CMiniFrameWnd` \(avec des options supplémentaires\) après construction.|  
  
## Notes  
 Ces fenêtres mini\-frame se comportent comme les fenêtres frames normales, mais qu'elles n'ont pas pour réduire\/agrandissent des boutons ou les menus et vous devez cliquer une seule fois dans le menu système pour les fermer.  
  
 Pour utiliser un objet d' `CMiniFrameWnd` , définissez d'abord l'objet.  Appelez la fonction membre de [Create](../Topic/CMiniFrameWnd::Create.md) pour afficher la fenêtre mini\-frame.  
  
 Pour plus d'informations sur l'utilisation des objets d' `CMiniFrameWnd` , consultez l'article [L'ancrage et barres d'outils flottante](../../mfc/docking-and-floating-toolbars.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)