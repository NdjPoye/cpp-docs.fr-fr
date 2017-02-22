---
title: "Onglets et attributs de contr&#244;le d&#39;onglet | Microsoft Docs"
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
  - "attributs (C++), rubriques de référence"
  - "CTabCtrl (classe), attributs de contrôle onglet"
  - "contrôles onglet, attributs"
  - "onglets"
  - "onglets, attributs"
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Onglets et attributs de contr&#244;le d&#39;onglet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous avez le contrôle considérable de l'apparence et le comportement des onglets qui composent un contrôle onglet \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\).  Chaque onglet peut avoir un nom, une icône, un état de l'élément, et une valeur 32 bits définis par l'application associée à celui\-ci.  Pour chaque onglet, vous pouvez afficher l'icône, le nom, ou les deux.  
  
 De plus, chaque élément de l'onglet peut contenir trois états possibles : enfoncé, enfoncé, ou mises en surbrillance.  Cet état peut être défini lors de la modification d'un élément existant de l'onglet.  Pour modifier un élément existant de l'onglet, récupérez\- le par un appel à [GetItem](../Topic/CTabCtrl::GetItem.md), modifiez la structure d'`TCITEM` \(notamment les membres de données de **dwState** et de **dwStateMask** \), puis retourner la structure d'`TCITEM` modifiée par un appel à [SetItem](../Topic/CTabCtrl::SetItem.md).  Si vous devez supprimer les états du tous les éléments de l'onglet dans `CTabCtrl` objet, effectuez un appel à [DeselectAll](../Topic/CTabCtrl::DeselectAll.md).  Cette fonction réinitialise l'état de tous les éléments de tabulation ou de tous les éléments sauf celui sélectionné.  
  
 Le code suivant désactive l'état de tous les éléments de l'onglet puis modifie l'état du troisième élément :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/CPP/tabs-and-tab-control-attributes_1.cpp)]  
  
 Pour plus d'informations sur les attributs de l'onglet, consultez l'[Onglets et attributs de l'Onglet](http://msdn.microsoft.com/library/windows/desktop/bb760550) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Pour plus d'informations sur les onglets d'ajout à un contrôle onglet, consultez l'[Onglets d'ajout à un contrôle onglet](../mfc/adding-tabs-to-a-tab-control.md) plus loin dans cette rubrique.  
  
## Voir aussi  
 [Utilisation de CTabCtrl](../mfc/using-ctabctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)