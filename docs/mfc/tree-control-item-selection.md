---
title: "S&#233;lection d&#39;&#233;l&#233;ments de contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "contrôles (MFC), sélectionner des éléments"
  - "CTreeCtrl (classe), sélection d'éléments"
  - "sélection d'éléments dans les contrôles d'arborescence"
  - "contrôles d'arborescence, sélection d'éléments"
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;lection d&#39;&#233;l&#233;ments de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque la sélection change d'un élément à un autre, un contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) envoie les messages de notification [TVN\_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) et [TVN\_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544).  Les deux notifications incluent une valeur qui spécifie si la modification est le résultat d'un clic de souris ou d'une combinaison de touches.  Les notifications incluent également des informations sur l'élément qui gagne la sélection et l'élément qui perd la sélection.  Vous pouvez utiliser ces informations pour définir les attributs de l'élément qui dépendent de l'état de sélection de l'élément.  Renvoyer **TRUE** en réponse à **TVN\_SELCHANGING** empêche la sélection de changer ; renvoyer **FALSE** autorise la modification.  
  
 Une application peut modifier la sélection en appelant la fonction membre [SelectItem](../Topic/CTreeCtrl::SelectItem.md).  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)