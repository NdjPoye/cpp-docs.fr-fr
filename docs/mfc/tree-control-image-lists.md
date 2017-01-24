---
title: "Listes d&#39;images de contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), listes d'images"
  - "images (C++), listes dans les contrôles d'arborescence"
  - "contrôles d'arborescence, listes d'images"
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Listes d&#39;images de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque élément dans un contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) peut comporter une paire d'images bitmap qui lui sont associées.  Les images apparaissent à gauche du nom de l'élément.  Une image est affichée lorsque l'élément est sélectionné, l'autre est affichée lorsque l'élément n'est pas sélectionné.  Par exemple, un élément peut afficher un dossier ouvert lorsque est sélectionné et un dossier fermé lorsqu'il n'est pas sélectionnée.  
  
 Pour utiliser des images d'élément, vous devez créer une liste des images en construisant un objet d'[CImageList](../mfc/reference/cimagelist-class.md) et en cas de utilisation de la fonction d'[CImageList::Create](../Topic/CImageList::Create.md) pour créer la liste des images associée.  Ajoutez les images bitmap de votre choix dans la liste, puis associez la liste à l'aide de le contrôle d'arborescence à l'aide de la fonction membre d'[SetImageList](../Topic/CTreeCtrl::SetImageList.md).  Par défaut, tous les éléments affichent la première image dans la liste des images des états sélectionnés et nonselected.  Vous pouvez modifier le comportement par défaut pour un élément particulier en spécifiant les index des images sélectionnées et nonselected en ajoutant l'élément dans le contrôle d'arborescence à l'aide de la fonction membre d'[InsertItem](../Topic/CTreeCtrl::InsertItem.md).  Vous pouvez modifier les index après avoir ajouté un élément à l'aide de la fonction membre d'[SetItemImage](../Topic/CTreeCtrl::SetItemImage.md).  
  
 Les listes d'images d'un contrôle d'arborescence peut également contenir des images de chevauchement, conçues pour être chevauchées images d'élément.  Une valeur autre que zéro dans les bits 8 et 11 de l'état d'un élément de contrôle tree spécifie l'index de base 1 à une image de chevauchement \(0 indique une image de chevauchement\).  Les 4 bits, index en démarrant à 1 sont utilisés, les images de chevauchement doivent être entre les 15 premières images dans les listes des images.  Pour plus d'informations sur les états de arborescence, consultez l'[L'élément de arborescence indique la présentation](../mfc/tree-control-item-states-overview.md) plus haut dans cette rubrique.  
  
 Si une liste des images d'état est spécifiée, un espace de réserve de contrôle d'arborescence à gauche de l'icône de chaque élément d'une image d'état.  L'utilisation des images d'état, telles que des cases à cocher activées ou désactivées, vous permet d'indiquer des états définis par l'application pour des éléments.  Une valeur non nulle en 12 et 15 bits précise cet index binaire de l'état d'une image \(0 indique une image sans état\).  
  
 En spécifiant la valeur d'**I\_IMAGECALLBACK** au lieu de l'index d'une image, vous pouvez retarder spécifier l'image sélectionnée ou nonselected jusqu'à ce que l'élément est sur le point d'être repeinte.  **I\_IMAGECALLBACK** exécute l'arborescence pour interroger la demande d'index lors de l'envoi du message de notification d'[TVN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518).  
  
 La fonction membre d'[GetImageList](../Topic/CTreeCtrl::GetImageList.md) récupère le descripteur de la liste des images d'un contrôle d'arborescence.  Cette fonction est utile si vous devez ajouter des images à la liste.  Pour plus d'informations sur les listes des images, consultez [Utilisation CImageList](../mfc/using-cimagelist.md), [CImageList](../mfc/reference/cimagelist-class.md) dans *le guide de MFC*, et l'[Listes des images](http://msdn.microsoft.com/library/windows/desktop/bb761389) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)