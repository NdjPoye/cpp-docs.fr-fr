---
title: "Initialisation des documents et vues | Microsoft Docs"
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
  - "documents, initialiser"
  - "initialiser des documents"
  - "initialiser des objets, objets Document"
  - "Initialiser des vues"
  - "vues, initialiser"
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Initialisation des documents et vues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les documents sont créés de deux façons différentes, donc la classe de document doit prendre en charge les deux manières.  D'abord, l'utilisateur peut créer un nouveau document vide avec la commande Nouveau Fichier.  Dans ce cas, initialisez le document dans la substitution de la méthode [OnNewDocument](../Topic/CDocument::OnNewDocument.md) de la classe [CDocument](../mfc/reference/cdocument-class.md).  Ensuite, l'utilisateur peut utiliser la commande Ouvrir dans le menu Fichier pour créer un document dont le contenu est lu à partir d'un fichier.  Dans ce cas, initialisez le document dans la substitution de la méthode [OnNewDocument](../Topic/CDocument::OnOpenDocument.md) de la classe **CDocument**.  Si les deux initialisations sont identiques, vous pouvez appeler une méthode commune des deux substitutions, ou `OnOpenDocument` peut appeler `OnNewDocument` pour initialiser un document propre puis terminer l'opération d'ouverture.  
  
 Les vues sont créées après la création des documents.  Le meilleur moment pour lancer une vue est une fois que l'infrastructure a fini de créer le document, le cadre et la vue.  Vous pouvez initialiser l'affichage en remplaçant la méthode [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) de [CView](../mfc/reference/cview-class.md).  Si vous devez réinitialiser ou ajuster quelque chose chaque fois que le document change, vous pouvez remplacer [OnUpdate](../Topic/CView::OnUpdate.md).  
  
## Voir aussi  
 [Initialisation et nettoyage des documents et vues](../mfc/initializing-and-cleaning-up-documents-and-views.md)