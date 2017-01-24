---
title: "Cr&#233;ation des listes d&#39;images | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CListCtrl (classe), créer des listes d'images pour"
  - "listes d'images (C++), créer pour CListCtrl"
  - "listes (C++), image"
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation des listes d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Créer des listes d'images est identique que vous utilisiez [CListView](../mfc/reference/clistview-class.md) ou [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Vous n'avez besoin que de listes d'images si votre contrôle de liste inclut le style `LVS_ICON`.  
  
 Utilisez la classe `CImageList` pour créer une ou plusieurs listes d'images \(pour les grandes icônes, les petites icônes, et les états standard\).  Voir le [CImageList](../mfc/reference/cimagelist-class.md), et afficher [Listes des images en mode Liste](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Appelez [CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md) pour chaque liste des images ; passez un pointeur à l'objet approprié `CImageList`.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)