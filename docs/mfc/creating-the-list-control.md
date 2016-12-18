---
title: "Cr&#233;ation du contr&#244;le de liste | Microsoft Docs"
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
  - "CListCtrl (classe), créer un contrôle"
  - "contrôles de liste"
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation du contr&#244;le de liste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comment le contrôle de liste\([CListCtrl](../mfc/reference/clistctrl-class.md)\) est créé selon que vous utilisez le contrôle directement ou utilisez la classe [CListView](../mfc/reference/clistview-class.md) à la place.  Si vous utilisez `CListView`, l'infrastructure construit la vue dans le cadre de sa séquence de création de documents\/vue.  La création du mode Liste crée le contrôle de liste également \(les deux sont identiques\).  Le contrôle est créé dans la fonction gestionnaire de [OnCreate](../Topic/CWnd::OnCreate.md) de la vue.  Dans ce cas, le contrôle est prêt pour que l'ajout d'éléments, via un appel à [GetListCtrl](../Topic/CListView::GetListCtrl.md).  
  
### Pour utiliser CListeCtrl directement dans une boîte de dialogue  
  
1.  Dans l'éditeur de boîtes de dialogue, ajoutez une liste de contrôle dans votre ressource de modèle de dialogue.  Spécifiez son ID de contrôle  
  
2.  Utilisez [Assistant d'Ajout de variable membre](../ide/adding-a-member-variable-visual-cpp.md) pour ajouter une variable membre de type `CListCtrl` avec la propriété de contrôle.  Vous pouvez utiliser ce membre pour appeler des fonctions membres `CListCtrl`.  
  
3.  Utilisez la fenêtre Propriétés pour mapper les fonctions de gestion dans la classe de la boîte de dialogue pour toutes les messages de notifications de contrôle de listes \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
4.  Dans [SurInitialiserDialogue](../Topic/CDialog::OnInitDialog.md), définissez les styles pour `CListCtrl`.  Voir [Changer le style des listes de contrôle](../mfc/changing-list-control-styles.md).  Détermine le type de «vue» que vous obtenez dans le contrôle, bien que vous puissiez modifier la vue ultérieurement.  
  
### Pour utiliser CListCtrl dans une fenêtre boîte sans dialogue.  
  
1.  Définissez le contrôle d'une classe vue ou fenêtre.  
  
2.  Appelez la fonction membre [Créer](../Topic/CListCtrl::Create.md) du contrôle, éventuellement dans [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), éventuellement dans la fonction gestionnaire [OnCreate](../Topic/CWnd::OnCreate.md) parente de la fenêtre \(si vous sous\-classez le contrôle\).  Définissez les styles pour le contrôle.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)