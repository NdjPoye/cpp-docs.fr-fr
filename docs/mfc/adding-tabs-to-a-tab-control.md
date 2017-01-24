---
title: "Ajout d&#39;onglets &#224; un contr&#244;le Tab | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CTabCtrl (classe), ajouter des onglets"
  - "mettre des onglets sur des CTabCtrl"
  - "contrôles onglet, ajouter des onglets"
  - "onglets, ajouter à la classe CTabCtrl"
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;onglets &#224; un contr&#244;le Tab
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Après avoir créé un contrôle onglet \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\), ajoutez autant d'onglets que nécessaire.  
  
### Pour ajouter un élément onglet  
  
1.  Préparer une structure [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554).  
  
2.  Appelez [CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md), en passant la structure.  
  
3.  Répétez les étapes 1 et 2 pour les autres éléments d'onglet.  
  
 Pour plus d'informations, consultez  [Création de contrôles d'onglet](http://msdn.microsoft.com/library/windows/desktop/bb760550) dans le [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CTabCtrl](../mfc/using-ctabctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)