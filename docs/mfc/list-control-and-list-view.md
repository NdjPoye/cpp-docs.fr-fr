---
title: "Contr&#244;le de liste et vue Liste | Microsoft Docs"
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
  - "CListCtrl (classe), et CListView"
  - "CListView (classe), et CListCtrl"
  - "contrôles de liste, Liste (vue)"
  - "Liste (vues)"
  - "vues, liste et contrôle de liste"
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;le de liste et vue Liste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par commodité, MFC encapsule le contrôle de liste de deux manières.  Vous pouvez utiliser les contrôles de liste :  
  
-   Directement, en intégrant un objet [CListCtrl](../mfc/reference/clistctrl-class.md) dans une classe de la boîte de dialogue.  
  
-   Indirectement, à l'aide de la classe [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView` facilite l'intégration d'un contrôle de liste à l'architecture MFC documents\/Vue, encapsulant le contrôle comme  [CEditView](../mfc/reference/ceditview-class.md) encapsule un contrôle d'édition : le contrôle remplit la surface d'exposition entière d'une vue MFC. \(La vue *est* le contrôle, castée à `CListView`.\)  
  
 Un objet `CListView` hérite de [CCtrlView](../mfc/reference/cctrlview-class.md) et de ses classes de base et ajoute une fonction membre pour récupérer le contrôle de liste sous\-jacent.  Utilisez les membres de vue pour utiliser la vue comme une vue.  Utilisez la fonction membre [GetListCtrl](../Topic/CListView::GetListCtrl.md) pour accéder aux fonctions membres à partir du contrôle de liste.  Utilisez ces membres pour :  
  
-   Ajouter, supprimer, ou manipuler des « éléments » dans la liste.  
  
-   Définissez ou obtenez les attributs de contrôle de liste.  
  
 Pour obtenir une référence au `CListCtrl` sous\-jacent à une `CListView`, appelez `GetListCtrl` de la classe en vue de liste :  
  
 [!code-cpp[NVC_MFCListView#4](../mfc/codesnippet/CPP/list-control-and-list-view_1.cpp)]  
  
 Cette rubrique décrit les deux façons d'utiliser le contrôle de liste.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)