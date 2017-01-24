---
title: "Utilisation de CHeaderCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeaderCtrl (classe)"
  - "contrôles header, utilisation"
ms.assetid: fb3e512b-9539-43c4-a7e7-3fafd6d0706e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de CHeaderCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez un contrôle header, représenté par la classe [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md), pour afficher des en\-têtes de colonnes pour une liste colomnaire.  Par exemple, un contrôle header est utile pour implémenter des contrôles de colonne dans une feuille de calcul.  
  
 Le contrôle header est généralement divisé en parties, appelées « éléments d'en\-tête », portant chacun un titre pour la colonne associée du texte ou des nombres.  Selon les styles que vous définissez, vous pouvez fournir plusieurs moyens directs aux utilisateurs de manipuler les éléments d'en\-tête.  
  
> [!NOTE]
>  [CListCtrl](../mfc/reference/clistctrl-class.md) fournit un contrôle header incorporé, puis [CListView](../mfc/reference/clistview-class.md) encapsule `CListCtrl` dans une classe de MFC.  Pensez à utiliser en général `CHeaderCtrl` pour donner une étiquette aux listes que vous envisagez d'ajouter vous même.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Contrôle Header et contrôle List](../mfc/header-control-and-list-control.md)  
  
-   [Exemples de contrôle Header](../mfc/header-control-examples.md)  
  
-   [Éléments d'en\-tête dans un contrôle Header](../mfc/header-items-in-a-header-control.md)  
  
-   [Personnalisation de l'apparence de l'élément d'en\-tête](../mfc/customizing-the-header-item-s-appearance.md)  
  
-   [Prise en charge du glisser\-déplacer pour les éléments d'en\-tête](../mfc/providing-drag-and-drop-support-for-header-items.md)  
  
-   [Utilisation de listes d'images avec des contrôles Header](../mfc/using-image-lists-with-header-controls.md)  
  
-   [Rendre des contrôles header owner\-drawn](../mfc/making-owner-drawn-header-controls.md)  
  
-   [Utilisation d'un contrôle Header](../mfc/working-with-a-header-control.md)  
  
-   [Création du contrôle Header](../mfc/creating-the-header-control.md)  
  
-   [Ajout d'éléments au contrôle Header](../mfc/adding-items-to-the-header-control.md)  
  
-   [Organisation des éléments dans le contrôle Header](../mfc/ordering-items-in-the-header-control.md)  
  
-   [Traitement des notifications de contrôle Header](../mfc/processing-header-control-notifications.md)  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)