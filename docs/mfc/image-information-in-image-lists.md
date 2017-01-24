---
title: "informations relatives aux images dans les listes d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), informations relatives aux images dans"
  - "listes d'images (C++), informations relatives aux images dans"
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# informations relatives aux images dans les listes d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../mfc/reference/cimagelist-class.md) inclut plusieurs fonctions qui récupèrent les informations d'une liste des images.  La fonction membre [GetImageInfo](../Topic/CImageList::GetImageInfo.md) remplit la structure `IMAGEINFO` avec les informations relatives à une image, y compris les poignées de l'image bitmap et de filtrage, le nombre de plans et de bits de couleur par pixels, et du rectangle englobant de l'image dans la bitmap de l'image.  Vous pouvez utiliser ces informations pour manipuler directement les bitmap de l'image.  
  
 La fonction membre [GetImageCount](../Topic/CImageList::GetImageCount.md) récupère le nombre d'images dans une liste d'images.  
  
 Vous pouvez créer une icône sur une image et masquer une liste d'images à l'aide de la fonction membre [ExtractIcon](../Topic/CImageList::ExtractIcon.md).  La fonction retourne le descripteur de la nouvelle icône.  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)