---
title: "Utilisation de vues | Microsoft Docs"
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
  - "CView (classe), architecture vue"
  - "dessiner, données"
  - "interaction avec les utilisateurs et rôle de la classe de vue"
  - "MFC, vues"
  - "peinture (données)"
  - "rendu (données)"
  - "entrée d'utilisateur, interpréter via la classe de vue"
  - "classes vues, rôle dans l'affichage des données d'application"
  - "classes vues, rôle dans la gestion de l'interaction avec l'utilisateur"
  - "vues, utilisation"
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Utilisation de vues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les responsabilités de la vue sont d'afficher les données de ce graphique à l'utilisateur et de recevoir et d'interpréter une entrée utilisateur comme opérations sur le document.  Vos tâches lors de l'écriture de votre classe d'affichage sont de:  
  
-   Entrez la fonction membre de [OnDraw](../Topic/CView::OnDraw.md) de la classe de vue, qui affiche les données du document.  
  
-   Connectez les messages appropriés et les objets d'interface utilisateur Windows comme les éléments de menu aux fonctions membres responsables de messages dans la classe d'affichage.  
  
-   Implémentez ces gestionnaires pour interpréter les entrées utilisateur.  
  
 En outre, vous devrez peut\-être remplacer d'autres fonctions membres de `CView` dans la classe d'affichage dérivé.  En particulier, vous pouvez substituer [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) pour effectuer l'initialisation spéciale pour la vue et [OnUpdate](../Topic/CView::OnUpdate.md) pour effectuer un traitement spécial nécessaire juste avant la vue se rafraîchisse.  Pour les documents multipages, vous devez également remplacer [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) pour initialiser la boîte de dialogue Imprimer avec le nombre de pages à imprimer et d'autres informations.  Pour plus d'informations pour remplacer les fonctions membres de `CView`, consultez la classe [CView](../mfc/reference/cview-class.md) dans *le guide de MFC*.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Classes d'affichage dérivées disponibles dans MFC](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Dessin dans un affichage](../mfc/drawing-in-a-view.md)  
  
-   [Interprétation de l'entrée utilisateur via une vue](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Rôle de l'affichage dans l'impression](../mfc/role-of-the-view-in-printing.md)  
  
-   [Défilement et mise à l'échelle des vues](../mfc/scrolling-and-scaling-views.md)  
  
-   [Initialisation et nettoyage des documents et affichages](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)   
 [CFormView Class](../mfc/reference/cformview-class.md)   
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Ignorer le mécanisme de sérialisation](../mfc/bypassing-the-serialization-mechanism.md)