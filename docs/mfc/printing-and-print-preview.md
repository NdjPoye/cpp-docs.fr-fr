---
title: "Impression et aper&#231;u avant impression | Microsoft Docs"
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
  - "afficher un aperçu avant impression"
  - "aperçu avant impression"
  - "imprimer (C++)"
  - "imprimer (C++), aperçu avant impression"
  - "imprimer (MFC)"
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impression et aper&#231;u avant impression
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC prend en charge l'impression et l'aperçu avant impression pour les documents de votre programme via la classe [CView](../mfc/reference/cview-class.md).  Pour l'impression de base et l'aperçu avant impression, remplacez simplement la fonction membre de [OnDraw](../Topic/CView::OnDraw.md) de la classe d'affichage, ce que vous devrez effectuer de toute façon.  Cette fonction peut dessiner sur l'écran un contexte de l'imprimante pour une imprimante réelle, ou un contexte du périphérique qui simule votre imprimante à l'écran.  
  
 Vous pouvez également ajouter du code pour gérer l'impression multipage et l'aperçu du document, ainsi que pour paginer vos documents imprimés, et ajouter des en\-têtes et pieds de page à ceux\-ci.  
  
 La famille des articles explique comment la fonction d'impression est implémenté dans la bibliothèque MFC \(MFC\) et comment tirer parti de l'architecture d'impression déjà intégrée dans l'infrastructure.  Ces articles expliquent aussi comment l'aide MDF facilite l'implémentation de la fonctionnalité d'aperçu avant impression et comment vous pouvez utiliser et modifier cette fonctionnalité.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Impression](../mfc/printing.md)  
  
-   [Architecture de l'aperçu avant impression](../mfc/print-preview-architecture.md)  
  
-   [Exemple](../top/visual-cpp-samples.md)  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)