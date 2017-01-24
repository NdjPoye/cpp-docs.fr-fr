---
title: "Superpositions d&#39;images dans les listes d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), superpositions d'images dans"
  - "listes d'images (C++), superpositions d'images dans"
  - "superpositions"
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Superpositions d&#39;images dans les listes d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque liste d'images \([CImageList](../mfc/reference/cimagelist-class.md)\) comporte la liste des images à utiliser comme masques de superposition.  Un "masque de superposition" est une image dessinée de façon transparente sur une autre image.  Toute image peut être utilisée comme filtre de chevauchement.  Vous pouvez spécifier jusqu'à quatre masques de superposition par liste d'images.  
  
 Vous ajoutez l'index d'une image à la liste des masques de superposition à l'aide de la fonction membre [SetOverlayImage](../Topic/CImageList::SetOverlayImage.md), l'index d'une image, et l'index d'un masque de superposition.  Notez que les index des masques de superposition est de base 1 et non de base zéro.  
  
 Vous dessinez un masque de superposition sur une image en un seul appel à **Dessin**.  Les paramètres incluent l'index de l'image à ajouter et l'index d'un masque de superposition.  Vous devez utiliser la macro [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) pour spécifier l'index du masque de superposition.  Vous pouvez également spécifier une image de superposition en appelant la fonction membre [DrawIndirect](../Topic/CImageList::DrawIndirect.md).  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)