---
title: "Cr&#233;ation de bo&#238;tes de dialogue modales | Microsoft Docs"
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
  - "boîtes de dialogue MFC, créer"
  - "boîtes de dialogue MFC, modales"
  - "boîtes de dialogue modales, créer"
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Cr&#233;ation de bo&#238;tes de dialogue modales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour créer une boîte de dialogue modale, appelez l'un des deux constructeurs publics déclarés dans [CDialog](../mfc/reference/cdialog-class.md).  Ensuite, appelez la fonction membre d' [DoModal](../Topic/CDialog::DoModal.md) de l'objet de dialogue pour afficher la boîte de dialogue et gérer l'interaction avec elle jusqu'à ce que l'utilisateur choisisse OK ou Annuler.  Cette gestion par `DoModal` est ce qui rend la boîte de dialogue modale.  Pour les boîtes de dialogue modales, `DoModal` charge la ressource de la boîte de dialogue.  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)