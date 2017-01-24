---
title: "CTreeCtrl par rapport &#224; CTreeView | Microsoft Docs"
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
  - "CTreeCtrl"
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl (classe), différences par rapport à la classe CTreeView"
  - "CTreeView (classe), différences par rapport à la classe CTreeCtrl"
  - "contrôles d'arborescence, et arborescence"
  - "contrôles d'arborescence"
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl par rapport &#224; CTreeView
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit deux classes qui encapsulent les contrôles d'arborescence : [CTreeCtrl](../mfc/reference/ctreectrl-class.md) et [CTreeView](../mfc/reference/ctreeview-class.md).  Chaque classe est utile dans différentes situations.  
  
 Utilisez `CTreeCtrl` lorsque vous avez besoin d'un contrôle ordinaire de fenêtre enfant ; par exemple, dans une boîte de dialogue.  Vous souhaiteriez utiliser `CTreeCtrl` notamment s'il y a d'autres contrôles d'enfants dans la fenêtre, comme dans une boîte de dialogue standard.  
  
 Utilisez `CTreeView` lorsque vous souhaitez l'arborescence pour agir comme une fenêtre de visualisation dans l'architecture documents\/Vue ainsi qu'un contrôle d'arborescence.  `CTreeView` occupera la zone client entière d'une fenêtre cadre ou d'un point de fractionnement.  Elle sera automatiquement redimensionnée lorsque sa fenêtre parente est redimensionnée, et elle peut traiter les messages de commande dans les menus, les touches accélérateur, et les barres d'outils.  Étant donné qu'un contrôle d'arborescence contient les données nécessaires pour afficher l'arborescence, l'objet document correspondant n'a pas à être compliqué — vous pouvez même utiliser [CDocument](../mfc/reference/cdocument-class.md) comme type de document dans votre modèle de document.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)