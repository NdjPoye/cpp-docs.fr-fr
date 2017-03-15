---
title: "Manipulation de listes d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), manipuler"
  - "listes d'images (C++), manipuler"
  - "listes (C++), image"
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Manipulation de listes d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fonction membre [Remplacer](../Topic/CImageList::Replace.md) remplace une image dans une liste d'image \([CImageList](../mfc/reference/cimagelist-class.md)\) par une nouvelle image.  Cette fonction est également utile lorsque vous devez augmenter dynamiquement le nombre d'images dans un objet de liste d'images.  La fonction [SetImageCount](../Topic/CImageList::SetImageCount.md) modifie dynamiquement le nombre d'images stockées dans la liste des images.  Si vous augmentez la taille de la liste des images, appelez **Remplacer** pour ajouter des images vers les nouveaux emplacements d'image.  Si vous réduisez la taille de la liste des images, des images au delà de la nouvelle taille sont libérées.  
  
 La fonction membre [Supprimer](../Topic/CImageList::Remove.md) supprime une image d'une liste d'images.  La fonction membre [Copier](../Topic/CImageList::Copy.md) peut copier ou échanger des images dans une liste d'images.  Cette fonction permet d'indiquer si l'image source doit être copiée à l'index de destination ou si les images de source et de destination doivent être permutées.  
  
 Pour créer une nouvelle liste d'images en mélangeant deux listes d'images, utilisez la surcharge appropriée de la fonction membre [Créer](../Topic/CImageList::Create.md).  Cette surcharge de **Créer** fusionne la première image des listes d'images existantes, en inscrivant l'image obtenu dans un nouvel objet de liste d'images.  La nouvelle image est créée en traçant la deuxième image de façon transparente sur la première.  Le masque pour la nouvelle image est le résultat d'une opération OU logique sur les bits des masques pour les deux images existantes.  
  
 Cela est répété jusqu'à ce que toutes les images aient été fusionnées et ajoutées au nouvel objet de liste d'images.  
  
 Entrez des informations d'image vers une archive en appelant la fonction membre [Écriture](../Topic/CImageList::Write.md), puis y lire le moment en appelant la fonction membre [Lecture](../Topic/CImageList::Read.md).  
  
 Les fonctions membres [GetSafeHandle](../Topic/CImageList::GetSafeHandle.md), [Attacher](../Topic/CImageList::Attach.md), et [Détacher](../Topic/CImageList::Detach.md) vous permettent de manipuler le descripteur de la liste d'images associée à l'objet `CImageList`, tandis que la fonction membre [DeleteImageList](../Topic/CImageList::DeleteImageList.md) supprime la liste d'images sans détruire l'objet `CImageList`.  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)