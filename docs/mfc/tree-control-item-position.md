---
title: "Position d&#39;&#233;l&#233;ment de contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), position des éléments"
  - "position de éléments dans les contrôles d'arborescence"
  - "position, CTreeCtrl (éléments)"
  - "contrôles d'arborescence, position des éléments"
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Position d&#39;&#233;l&#233;ment de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La position initiale d'un élément est définie lorsque l'élément est ajouté au contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) à l'aide de la fonction membre `InsertItem`.  L'appel d'une fonction membre spécifie le descripteur de l'élément parent et le descripteur de l'élément après lequel le nouvel élément doit être inséré.  Le deuxième descripteur doit identifier un élément enfant du parent ou une des valeurs suivantes : `TVI_FIRST`, `TVI_LAST`, ou `TVI_SORT`.  
  
 Lorsque `TVI_FIRST` ou `TVI_LAST` est spécifié, l'arborescence place le nouvel élément au début ou à la fin de la liste parente donnée d'éléments enfants.  Lorsque `TVI_SORT` est spécifié, l'arborescence insère un nouvel élément dans la liste d'éléments enfants par ordre alphabétique en fonction du texte des noms d'éléments.  
  
 Vous pouvez mettre la liste parente d'éléments enfants dans l'ordre alphabétique en appelant la fonction membre [SortChildren](../Topic/CTreeCtrl::SortChildren.md).  Cette fonction contient un paramètre qui spécifie si tous les niveaux des éléments enfants descendants de l'élément parent donné sont également triés par ordre alphabétique.  
  
 La fonction membre [SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md) vous permet de trier les éléments enfants d'après les critères que vous définissez.  Lorsque vous appelez cette fonction, vous spécifiez une application \- appelée fonction de rappel que l'arborescence peut appeler chaque fois que l'ordre relatif de deux éléments enfants doit être établi.  La fonction de rappel reçoit deux valeurs 32 bits définies par l'application pour les éléments comparés et une troisième valeur 32 bits que vous spécifiez en appelant `SortChildrenCB`.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)