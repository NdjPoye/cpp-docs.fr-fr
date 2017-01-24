---
title: "Faire glisser des images &#224; partir d&#39;une liste d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), déplacer des images de"
  - "déplacer des images à partir de listes d'images"
  - "listes d'images (C++), déplacer des images de"
  - "images (C++), déplacer à partir de listes d'images"
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Faire glisser des images &#224; partir d&#39;une liste d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../mfc/reference/cimagelist-class.md) inclut des fonctions pour faire glisser une image sur l'écran.  Les fonctions de glissage déplace une image sans à coups, en couleurs, sans aucun clignotement du curseur.  Les images masquées et démasquées peuvent être glissées.  
  
 La fonction membre [BeginDrag](../Topic/CImageList::BeginDrag.md) démarre une opération glisser\-déplacer.  Les paramètres incluent l'index de l'image à faire glisser et l'emplacement de la zone réactive dans l'image.  La zone réactive est un seul pixel que les fonctions de glissage identifient comme l'emplacement exact de l'image à l'écran .  Généralement, une application définit la zone réactive afin qu'elle coïncide avec la zone réactive du curseur de la souris.  La fonction membre [DragMove](../Topic/CImageList::DragMove.md) déplace l'image vers un nouvel emplacement.  
  
 La fonction membre [DragEnter](../Topic/CImageList::DragEnter.md) définit la position initiale de l'image glissée dans la fenêtre et dessine l'image à la place.  Les paramètres incluent un pointeur vers la fenêtre dans laquelle ajouter l'image et un point qui spécifie les détails de la position initiale dans la fenêtre.  Les coordonnées sont exprimées par rapport au coin supérieur gauche de la fenêtre, pas de la zone cliente.  Il en va de même pour tous les fonctions de glissage d'image qui prennent des coordonnées en paramètres.  Cela signifie que vous devez compenser la largeur des éléments de la fenêtre, telles que la bordure, la barre de titre, et la barre de menus, lors de la spécification des coordonnées.  Si vous spécifiez un handle de fenêtre **NULL** en appelant `DragEnter`, les fonctions de glissages dessinent l'image dans le contexte de périphérique associé à la fenêtre de bureau, et les coordonnées sont relatives au coin supérieur gauche de l'écran.  
  
 `DragEnter` verrouille toutes les mises à jour dans la fenêtre données pendant l'opération de glissement.  Si vous devez effectuer un dessin au cours d'une opération glisser\-déplacer, telles que la mise en surbrillance de la cible d'une opération de glisser\-déplacer, vous pouvez masquer temporairement l'image à l'aide de la fonction membre [DragLeave](../Topic/CImageList::DragLeave.md).  Vous pouvez également utiliser la fonction membre [DragShowNoLock](../Topic/CImageList::DragShowNolock.md).  
  
 Appelez [EndDrag](../Topic/CImageList::EndDrag.md) lorsque vous avez terminé de faire glisser l'image.  
  
 La fonction membre [SetDragCursorImage](../Topic/CImageList::SetDragCursorImage.md) crée une nouvelle image glissée en combinant l'image donnée \(généralement une image de curseur de la souris\) avec l'image glissée actuelle.  Comme les fonctions de glissage utilisent la nouvelle image lors d'une opération glisser\-déplacer, vous devez utiliser la fonction [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) Windows pour masquer le curseur de la souris réel après avoir appelé `SetDragCursorImage`.  Sinon, le système peut sembler être composée de deux curseurs de souris pour la durée de l'opération glisser\-déplacer.  
  
 Lorsqu'une application appelle `BeginDrag`, le système crée une liste d'images temporaire interne et copie l'image glissée spécifiée à la liste interne.  Vous pouvez récupérer un pointeur vers la liste temporaire d'image glissée à l'aide de la fonction membre [GetDragImage](../Topic/CImageList::GetDragImage.md).  La fonction récupère également l'emplacement actuel de glisser\-déplacer et le décalage de l'image glissée par rapport à la position de glisser\-déplacer.  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)