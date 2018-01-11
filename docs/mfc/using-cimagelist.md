---
title: Utilisation de CImageList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImageList
dev_langs: C++
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 053e670b5a6d932c50e2f967ee38cf9191710ff4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-cimagelist"></a>Utilisation de CImageList
Une liste d’images, représentée par la classe [CImageList](../mfc/reference/cimagelist-class.md), est une collection d’images de même taille, chacun d’eux peut être référencé par son index. Listes d’images sont utilisées pour gérer efficacement les grands ensembles d’icônes ou de bitmaps. Listes d’images pas eux-mêmes sont des contrôles, car ils ne sont pas windows ; Toutefois, ils sont utilisés avec différents types de contrôles, y compris les contrôles de liste ([CListCtrl](../mfc/reference/clistctrl-class.md)), contrôles d’arborescence ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) et les contrôles de tabulation ([CTabCtrl](../mfc/reference/ctabctrl-class.md)).  
  
 Toutes les images dans une liste d’images sont contenues dans une seule grande bitmap au format de l’appareil à l’écran. Une liste d’images peut-être également inclure une image bitmap monochrome contenant des masques utilisés pour dessiner des images en toute transparence (style d’icône). `CImageList`Fournit des fonctions membres qui vous permettent de dessiner des images, créer et détruire des listes d’images, ajouter et supprimer des images, remplacer les images, fusionner des images et faire glisser des images.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Types de listes d’images](../mfc/types-of-image-lists.md)  
  
-   [Utilisation d’une liste d’images](../mfc/using-an-image-list.md)  
  
-   [Manipulation de listes d’images](../mfc/manipulating-image-lists.md)  
  
-   [Dessin d’images à partir d’une liste d’images](../mfc/drawing-images-from-an-image-list.md)  
  
-   [Superpositions d’images dans les listes d’images](../mfc/image-overlays-in-image-lists.md)  
  
-   [Faire glisser des images à partir d’une liste d’images](../mfc/dragging-images-from-an-image-list.md)  
  
-   [Informations relatives aux images dans les listes d’images](../mfc/image-information-in-image-lists.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)

