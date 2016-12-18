---
title: "Portrait de l&#39;architecture document/vue | Microsoft Docs"
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
  - "architecture document/vue"
  - "architecture document/vue, à propos de l'architecture document/vue (C++)"
  - "architecture document/vue, accéder aux données à partir d'une vue"
  - "documents, accéder aux données à partir d'une vue"
  - "documents, vues multiples"
  - "documents, vues"
  - "entrée, view (classe)"
  - "vues multiples, mettre à jour à partir d'un document"
  - "vues, accéder aux données de documents à partir de"
  - "vues, et entrée d'utilisateur"
  - "vues, mettre à jour"
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Portrait de l&#39;architecture document/vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les documents et les vues sont appariés dans une application classique MFC.  Les données sont stockées dans le document, mais la vue a un accès privilégié aux données.  La séparation du document de la vue sépare le stockage et la gestion des données de son affichage.  
  
## Accéder aux données de document de la vue  
 La vue accède aux données de son document soit avec la fonction [GetDocument](../Topic/CView::GetDocument.md), qui retourne un pointeur vers le document, ou en faisant de la classe un objet C\+\+ `friend` de la classe de document.  La vue utilise ensuite l'accès aux données pour obtenir les données lorsqu'il est prêt à dessiner ou manipuler d'une autre façon.  
  
 Par exemple, de la méthode [OnDraw](../Topic/CView::OnDraw.md) de la vue, la vue utilise **GetDocument** pour obtenir un pointeur de document.  Elle utilise ce pointeur pour accéder à un membre de données `CString` dans le document.  La vue passe la chaîne à la fonction `TextOut`.  Pour afficher le code pour cet exemple, consultez [Dessiner dans une vue](../mfc/drawing-in-a-view.md).  
  
## Entrée à la vue  
 La vue peut également interpréter un clic de souris dans elle\-même comme une sélection ou modification des données.  De même elle peut interpréter les séquences de clés comme entrée de données ou modification.  Supposons que l'utilisateur entre une chaîne dans une vue qui gère le texte.  La vue obtient un pointeur au document et utilise le pointeur pour passer les nouvelles données au document, qui l'enregistre dans une certaine structure de données.  
  
## Mettre à jour plusieurs vues du même document  
 Dans une application avec plusieurs vues du même document — telles qu'une fenêtre séparée dans un éditeur de texte — la vue passe d'abord les nouvelles données du document.  Elle appelle ensuite la méthode [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) du document, qui dit à toutes les vues du document de se mettre à jour, en renvoyant les nouvelles données.  Ceci synchronise les vues.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Avantages de l'architecture document\/vue](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Solutions de remplacement de l'architecture document\/vue](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)