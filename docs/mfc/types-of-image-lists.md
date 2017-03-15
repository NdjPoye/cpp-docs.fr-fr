---
title: "Types de listes d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), types"
  - "listes d'images (C++), types de"
  - "listes (C++), image"
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Types de listes d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe deux types de pools d'image \([CImageList](../mfc/reference/cimagelist-class.md)\) : non\-masqué et masqué.  Une "liste des images non\-masquées" consiste en une bitmap de couleur qui contient un ou plusieurs images.  Une "liste des images masquée" comprend deux bitmap de taille identique.  Le premier est un bitmap de couleur qui contient les images, et le second est un bitmap de monochrome qui contient une série de masques \(un pour chaque image de la première bitmap.  
  
 L'une des surcharges de la fonction membre **Créer** prend un indicateur pour indiquer si la liste des images est masquée ou non. \(Les autres surcharges créent des listes d'images masquées.\)  
  
 Lorsqu'une image non\-masquée est dessinée, elle est simplement copiée dans le contexte du périphérique cible ; autrement dit, elle est dessinée sur la couleur d'arrière\-plan existante du contexte de périphérique.  Lorsqu'une image masquée est dessinée, les bits de l'image sont combinés avec les bits du masque, produisant généralement des zones transparentes dans la bitmap, là où la couleur d'arrière\-plan du contexte de périphérique cible est visible.  Vous pouvez spécifier plusieurs styles de dessin lors du dessin d'une image masquée.  Par exemple, vous pouvez spécifier que l'image doit trembler pour indiquer un objet sélectionné.  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)