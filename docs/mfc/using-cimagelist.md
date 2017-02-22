---
title: "Utilisation de CImageList | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList (classe), utilisation"
  - "liste des images (contrôle)"
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation de CImageList
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une liste d'images, représentée par la classe [CImageList](../mfc/reference/cimagelist-class.md), est un ensemble d'images de même taille, qui peuvent être référencées par leurs indices.  Les listes d'images sont utilisées pour gérer efficacement des jeux d'icônes ou bitmaps.  Les listes d'images ne sont pas elles\-mêmes des contrôles puisqu'elles ne sont pas des fenêtres; toutefois, elles sont utilisées avec différents types de contrôles, notamment les contrôles de liste \([CListCtrl](../mfc/reference/clistctrl-class.md)\), les contrôles d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\), et les contrôles de tabulation \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\).  
  
 Toutes les images dans une liste d'images sont contenues dans une seule bitmap large dans le format d'affichage.  Une liste d'images peut également inclure une bitmap monochrome qui contient les masques utilisés pour ajouter des images de façon transparente \(style d'icône\).  `CImageList` fournit les méthodes qui vous permettent d'ajouter des images, créer et détruire des listes d'images, ajouter et supprimer des images, remplacer des images, fusionner des images, et déplacer des images.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Types de listes d'images](../mfc/types-of-image-lists.md)  
  
-   [Utilisation d'une liste d'images](../mfc/using-an-image-list.md)  
  
-   [Manipulation de listes d'images](../mfc/manipulating-image-lists.md)  
  
-   [Dessin d'images à partir d'une liste d'images](../mfc/drawing-images-from-an-image-list.md)  
  
-   [Superpositions d'images dans les listes d'images](../mfc/image-overlays-in-image-lists.md)  
  
-   [Faire glisser des images à partir d'une liste d'images](../mfc/dragging-images-from-an-image-list.md)  
  
-   [Informations relatives aux images dans les listes d'images](../mfc/image-information-in-image-lists.md)  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)