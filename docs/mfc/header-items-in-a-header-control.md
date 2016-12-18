---
title: "&#201;l&#233;ments d&#39;en-t&#234;te dans un contr&#244;le Header | Microsoft Docs"
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
  - "CHeaderCtrl (classe), éléments d'en-tête dans"
  - "contrôles (MFC), header"
  - "contrôles header, éléments d'en-tête dans"
  - "éléments d'en-tête dans les contrôles header"
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;l&#233;ments d&#39;en-t&#234;te dans un contr&#244;le Header
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous avez un contrôle considérable sur l'apparence et le comportement des éléments d'en\-tête qui composent un contrôle header \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\).  Chaque élément d'en\-tête peut avoir une chaîne, une image bitmap, une image d'une liste d'image associée, ou une valeur 32 bits définies par l'application associée à celui\-ci.  La chaîne, la bitmap, ou l'image est affichée dans l'élément d'en\-tête.  
  
 Vous pouvez personnaliser l'apparence et le contenu des éléments lorsqu'ils sont créés lors d'un appel [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md) ou en modifiant un élément existant, par un appel à [CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md) et [CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Personnalisation de l'apparence de l'élément d'en\-tête](../mfc/customizing-the-header-item-s-appearance.md)  
  
-   [Organisation des éléments dans le contrôle Header](../mfc/ordering-items-in-the-header-control.md)  
  
-   [Prise en charge du glisser\-déposer pour les éléments d'en\-tête](../mfc/providing-drag-and-drop-support-for-header-items.md)  
  
-   [Utilisation de listes d'images avec des contrôles Header](../mfc/using-image-lists-with-header-controls.md)  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)