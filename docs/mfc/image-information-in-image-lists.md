---
title: "Dans les listes d’images d’image | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33248c1bbc225d8d1ccf55c126d1657d0b0e4cad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="image-information-in-image-lists"></a>informations relatives aux images dans les listes d'images
[CImageList](../mfc/reference/cimagelist-class.md) inclut un certain nombre de fonctions qui récupèrent des informations à partir d’une liste d’images. Le [fonction membre GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) fonction membre remplit une `IMAGEINFO` structure avec des informations sur une seule image, y compris les handles de l’image et le masque les bitmaps, le nombre de plans de couleur et de bits par pixel et le rectangle englobant de l’image dans la bitmap de l’image. Vous pouvez utiliser ces informations pour manipuler directement les bitmaps de l’image.  
  
 Le [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) fonction membre récupère le nombre d’images dans une liste d’images.  
  
 Vous pouvez créer une icône basée sur une image et le masque dans une liste d’images à l’aide de la [fonction membre ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) fonction membre. La fonction retourne le handle de la nouvelle icône.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)

