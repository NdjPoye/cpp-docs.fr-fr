---
title: "CFormView Class | Microsoft Docs"
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
  - "CFormView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFormView class"
  - "form views"
  - "vues, containing controls"
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFormView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe de base utilisée pour les modes formulaire.  
  
## Syntaxe  
  
```  
class CFormView : public CScrollView  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CFormView::CFormView](../Topic/CFormView::CFormView.md)|Construit un objet `CFormView`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFormView::IsInitDlgCompleted](../Topic/CFormView::IsInitDlgCompleted.md)|Utilisé pour la synchronisation pendant l'initialisation.|  
  
## Notes  
 En substance, me mode Formulaire est une vue qui contient des contrôles.  La disposition de ces contrôles est basée sur une ressource de modèle de boîte de dialogue.  Utilisez `CFormView` si vous voulez des formulaires dans votre application.  Ces vues prennent en charge le défilement, le cas échéant, grâce à la fonctionnalité [CScrollView](../../mfc/reference/cscrollview-class.md).  
  
 Au moment de [créer une application basée sur les formulaires](../../mfc/reference/creating-a-forms-based-mfc-application.md), vous pouvez baser sa classe de vue sur `CFormView`, ce qui en fait une application basée sur les formulaires.  
  
 Vous pouvez aussi insérer de nouveaux [sujets de formulaire](../../mfc/form-views-mfc.md) dans les applications basées sur une architecture document\/vue.  Même si, au départ, votre application ne prend pas en charge les formulaires, Visual C\+\+ ajoute cette prise en charge du moment que vous insérez un nouveau formulaire.  
  
 L'Assistant Application MFC et la commande Ajouter une classe sont les méthodes recommandées pour créer des applications basées sur les formulaires.  Si vous devez créer une application basée sur les formulaires sans utiliser ces méthodes, consultez [Création d'une application basée sur les formulaires](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## Configuration requise  
 **En\-tête :**afxext.h  
  
## Voir aussi  
 [Exemple MFC SNAPVW](../../top/visual-cpp-samples.md)   
 [Exemple MFC VIEWEX](../../top/visual-cpp-samples.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CView::OnUpdate](../Topic/CView::OnUpdate.md)   
 [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)   
 [CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)