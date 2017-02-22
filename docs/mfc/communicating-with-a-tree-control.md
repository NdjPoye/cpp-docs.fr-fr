---
title: "Communication avec un contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "communications, contrôles d'arborescence"
  - "CTreeCtrl (classe), appeler les fonctions membres"
  - "contrôles d'arborescence"
  - "contrôles d'arborescence, communiquer avec"
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Communication avec un contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous utilisez différentes méthodes pour appeler des fonctions membres dans un objet [CTreeCtrl](../mfc/reference/ctreectrl-class.md) selon la façon dont l'objet a été créé :  
  
-   Si le contrôle tree est dans une boîte de dialogue, utilisez une variable membre de type `CTreeCtrl` que vous créez dans la classe de la boîte de dialogue.  
  
-   Si le contrôle tree est une fenêtre enfant, utilisez l'objet `CTreeCtrl` \(ou le pointeur\) que vous construisiez l'objet.  
  
-   Si vous utilisez un objet `CTreeView`, utilisez la fonction [CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md) pour obtenir une référence au contrôle d'arborescence.  Vous pouvez initialiser une autre référence à cette valeur ou modifier l'adresse de la référence à un pointeur `CTreeCtrl`.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)