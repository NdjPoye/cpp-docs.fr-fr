---
title: "R&#244;le de la vue dans l&#39;impression | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CView (classe), rôle dans l'impression"
  - "OnDraw (méthode), et impression"
  - "imprimer (MFC), OnDraw (méthode)"
  - "imprimer (MFC), vues"
  - "imprimer des vues"
  - "vues, imprimer"
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# R&#244;le de la vue dans l&#39;impression
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Your view also plays two important roles in printing its associated document.  
  
 The view:  
  
-   Uses the same [OnDraw](../Topic/CView::OnDraw.md) code to draw on the printer as to draw on the screen.  
  
-   Manages dividing the document into pages for printing.  
  
 For more information about printing and about the view's role in printing, see [Printing and Print Preview](../mfc/printing-and-print-preview.md).  
  
## Voir aussi  
 [Utilisation de vues](../mfc/using-views.md)