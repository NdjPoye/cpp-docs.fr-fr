---
title: "Organisation des &#233;l&#233;ments dans le contr&#244;le Header | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DS_DRAGDROP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DS_DRAGDROP (notification)"
  - "GetOrderArray (méthode)"
  - "contrôles header, organiser les éléments"
  - "OrderToIndex (méthode)"
  - "séquence"
  - "séquence, header (éléments de contrôle)"
  - "SetOrderArray (méthode)"
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Organisation des &#233;l&#233;ments dans le contr&#244;le Header
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fois que vous avez [éléments ajoutés à un contrôle header](../mfc/adding-items-to-the-header-control.md), vous pouvez manipuler ou obtenir des informations sur leur ordre avec les fonctions suivantes :  
  
-   [CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md) et [CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)  
  
     Récupère et définit l'ordre de gauche à droite des éléments d'en\-tête.  
  
-   [CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md).  
  
     Récupère la valeur d'index d'un élément d'en\-tête spécifique.  
  
 Outre les fonctions membres précédentes, le style `HDS_DRAGDROP` autorise l'utilisateur aux éléments d'en\-tête faire glisser dans le contrôle header.  Pour plus d'informations, consultez [Maintien de la prise en charge par glisser\-déplacer des éléments d'en\-tête](../mfc/providing-drag-and-drop-support-for-header-items.md).  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)