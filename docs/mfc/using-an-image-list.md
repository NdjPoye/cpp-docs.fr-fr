---
title: "Utilisation d&#39;une liste d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), utilisation"
  - "listes d'images (C++)"
  - "listes (C++), image"
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation d&#39;une liste d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation standard d'une liste des images suit le modèle ci\-dessous:  
  
-   Construisez un objet de [CImageList](../mfc/reference/cimagelist-class.md) et appelez l'une des surcharges de sa fonction de [Créer](../Topic/CImageList::Create.md) pour créer une liste des images et la joindre à l'objet de `CImageList`.  
  
-   Si vous n'ajoutez pas d'images lors de la création de la liste des images, ajouter des images à la liste des images en appelant la fonction membre [Ajouter](../Topic/CImageList::Add.md) ou [Lecture](../Topic/CImageList::Read.md).  
  
-   Associez la liste des images à un contrôle en appelant la fonction membre approprié pour ce contrôle, les images d'aspiration de la liste des images vous\-même utilisation de la fonction membre [Dessinez](../Topic/CImageList::Draw.md) de la liste des images.  
  
-   Peut\-être autoriser l'utilisateur à faire glisser une image, à la prise en charge intégrée de la liste des images pour les opérations de glissement.  
  
> [!NOTE]
>  Si la liste des images a été créée avec l'opérateur de **new**, vous devez détruire l'objet `CImageList` lorsque vous en avez terminé avec lui.  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)