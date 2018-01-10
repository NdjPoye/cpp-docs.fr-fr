---
title: "Types de listes d’images | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84a2118978d5ebd722d4fe56cdeec2aa0f74a94e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-image-lists"></a>Types de listes d'images
Il existe deux types de listes d’images ([CImageList](../mfc/reference/cimagelist-class.md)) : non masquées et masquées. Une « liste d’image non masquée » se compose d’une image bitmap de couleur qui contient une ou plusieurs images. Une « liste d’images masquées » se compose de deux bitmaps de taille égale. Le premier est une image bitmap de couleur qui contient les images, et le second est un bitmap monochrome contenant une série de masques, un pour chaque image de la première bitmap.  
  
 Une des surcharges de la **créer** fonction membre prend un indicateur pour indiquer si la liste d’images est masquée. (Les autres surcharges de créent des listes d’images masquées.)  
  
 Lorsqu’une image non masquée est dessinée, elle est simplement copiée dans le contexte de périphérique cible ; Autrement dit, elle est dessinée sur la couleur d’arrière-plan existante du contexte de périphérique. Lorsqu’une image masquée est dessinée, les bits de l’image sont combinés avec les bits du masque, produit généralement où la couleur d’arrière-plan du contexte de périphérique cible apparaît à travers les zones transparentes dans l’image bitmap. Vous pouvez spécifier plusieurs styles de dessin lorsque vous dessinez une image masquée. Par exemple, vous pouvez spécifier que l’image sera tramée pour indiquer un objet sélectionné.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)

