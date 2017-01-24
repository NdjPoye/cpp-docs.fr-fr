---
title: "Utilisation de listes d&#39;images dans un contr&#244;le de zone de liste d&#233;roulante &#233;tendue | Microsoft Docs"
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
  - "zones de liste déroulante étendues, images"
  - "listes d'images (C++), zones de liste déroulante"
  - "images (C++), éléments de zone de liste déroulante"
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de listes d&#39;images dans un contr&#244;le de zone de liste d&#233;roulante &#233;tendue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The main feature of extended combo box controls is the ability to associate images from an image list with individual items in a combo box control.  Each item is able to display three different images: one for its selected state, one for its nonselected state, and a third for an overlay image.  
  
 The following procedure associates an image list with an extended combo box control:  
  
### To associate an image list with an extended combo box control  
  
1.  Construct a new image list \(or use an existing image list object\), using the [CImageList](../mfc/reference/cimagelist-class.md) constructor and storing the resultant pointer.  
  
2.  Initialize the new image list object by calling [CImageList::Create](../Topic/CImageList::Create.md).  The following code is one example of this call.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  Add optional images for each possible state: selected or nonselected, and an overlay.  The following code adds three predefined images.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  Associate the image list with the control with a call to [CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md).  
  
 Once the image list has been associated with the control, you can individually specify the images each item will use for the three possible states.  For more information, see [Setting the Images for an Individual Item](../mfc/setting-the-images-for-an-individual-item.md).  
  
## Voir aussi  
 [Utilisation de CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Contrôles](../mfc/controls-mfc.md)