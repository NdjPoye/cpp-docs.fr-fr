---
title: "CHtmlEditView Class | Microsoft Docs"
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
  - "CHtmlEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditView class"
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de la plateforme de modification WebBrowser dans le contexte de l'architecture Document\/Vue MFC.  
  
## Syntaxe  
  
```  
  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase< CHtmlEditView >  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHtmlEditView::CHtmlEditView](../Topic/CHtmlEditView::CHtmlEditView.md)|Construit un objet `CHtmlEditView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHtmlEditView::Create](../Topic/CHtmlEditView::Create.md)|Crée un nouvel objet window.|  
|[CHtmlEditView::GetDHtmlDocument](../Topic/CHtmlEditView::GetDHtmlDocument.md)|Retourne l'interface d' **IHTMLDocument2** sur le document actif.|  
|[CHtmlEditView::GetStartDocument](../Topic/CHtmlEditView::GetStartDocument.md)|Extrait le nom du document par défaut de cette vue.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## Configuration requise  
 **Header:** afxhtml.h  
  
## Voir aussi  
 [Exemple HTMLEdit](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)