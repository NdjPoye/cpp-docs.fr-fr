---
title: "Classes associ&#233;es aux contr&#244;les RichEdit | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), associées aux contrôles RichEdit"
  - "CRichEditCtrl (classe), classes associées"
  - "CRichEditCtrlItem (classe) et CRichEditCtrl"
  - "CRichEditDoc (classe), RichEdit (contrôles)"
  - "CRichEditView (classe), et CRichEditCtrl"
  - "contrôles RichEdit, et CRichEditDoc"
  - "contrôles RichEdit, et CRichEditItem"
  - "contrôles RichEdit, et CRichEditView"
  - "contrôles RichEdit, classes associées à"
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes associ&#233;es aux contr&#244;les RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes [CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) fournissent des fonctionnalités du contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) dans le contexte de l'architecture documents\/vue MFC.  `CRichEditView` contient le texte et les caractéristiques de mise en forme du texte.  `CRichEditDoc` contient la liste d'éléments clients OLE contenus dans la vue.  `CRichEditCntrItem` permet d'accéder au côté conteneur de l'élément client OLE.  Pour modifier le contenu de `CRichEditView`, utilisez [CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md) pour accéder au contrôle RichEdit sous\-jacent.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)