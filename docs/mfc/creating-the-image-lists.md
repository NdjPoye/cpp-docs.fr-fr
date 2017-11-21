---
title: "Création de listes d’images | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4878caa735562a76bc4afe64b7d5bb1ecb22e069
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-image-lists"></a>Création des listes d'images
Création de listes d’images est le même que vous utilisiez [CListView](../mfc/reference/clistview-class.md) ou [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Vous seulement devez listes d’images si votre contrôle de liste comprend le `LVS_ICON` style.  
  
 Utilisez la classe `CImageList` pour créer un ou plusieurs listes d’images (pour les grandes icônes, les petites icônes et les États). Consultez [CImageList](../mfc/reference/cimagelist-class.md)et consultez [liste de listes d’images d’affichage](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans le Kit de développement logiciel Windows.  
  
 Appelez [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) pour chaque liste d’images ; passer un pointeur vers le `CImageList` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

