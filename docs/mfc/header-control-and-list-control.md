---
title: "Contr&#244;le Header et contr&#244;le List | Microsoft Docs"
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
  - "CHeaderCtrl (classe), avec CListCtrl"
  - "CListCtrl (classe), contrôles header"
  - "CListCtrl (classe), avec CHeaderCtrl"
  - "contrôles (MFC), header"
  - "contrôles header"
  - "contrôles header, contrôles de liste utilisés avec"
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Contr&#244;le Header et contr&#244;le List
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la plupart des cas, vous utilisez le contrôle header incorporé dans un objet [CListCtrl](../mfc/reference/clistctrl-class.md) ou [CListView](../mfc/reference/clistview-class.md).  Toutefois, il existe des cas où un objet de contrôle header disctinc est souhaitable, comme la manipulation des données, organisées dans des colonnes ou des lignes, dans un objet dérivé de [CView](../mfc/reference/cview-class.md).  Dans ce cas, vous devez disposer d'un contrôle optimisé d'apparence et du comportement par défaut d'un contrôle header incorporé.  
  
 Dans le cas courant où vous voulez un contrôle header pour fournir le comportement par défaut, vous pouvez utiliser [CListCtrl](../mfc/reference/clistctrl-class.md) ou [CListView](../mfc/reference/clistview-class.md) à la place.  Utilisez `CListCtrl` lorsque vous souhaitez les fonctionnalités d'un contrôle header par défaut, incorporé dans un contrôle courant de Liste.  Utilisez [CListView](../mfc/reference/clistview-class.md) lorsque vous souhaitez les fonctionnalités d'un contrôle header par défaut, incorporé dans un objet de vue.  
  
> [!NOTE]
>  Ces contrôles incluent uniquement un contrôle header intégré si le contrôle de vue de liste est créé avec le style `LVS_REPORT`.  
  
 Dans la plupart des cas, l'apparence du contrôle header incorporé peut être modifiée en modifiant les styles de contrôle de vue de liste conteneur.  En outre, les informations sur le contrôle header peuvent être obtenues via les fonctions membres du contrôle de vue de liste parent.  Toutefois, pour un contrôle total, et l'accès aux attributs et aux styles de contrôle header incorporé, il est recommandé que pointeur vers l'objet de contrôle header soit obtenu.  
  
 L'objet incorporé de contrôle header est accessible de **CListCtrl** ou `CListView` par un appel à la fonction membre `GetHeaderCtrl` de la classe correspondante.  Le code suivant illustre cette méthode :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/CPP/header-control-and-list-control_1.cpp)]  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de listes d'images avec des contrôles Header](../mfc/using-image-lists-with-header-controls.md)  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)