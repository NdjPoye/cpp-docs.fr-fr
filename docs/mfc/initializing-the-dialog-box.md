---
title: "Initialisation de la bo&#238;te de dialogue | Microsoft Docs"
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
  - "initialiser des boîtes de dialogue"
  - "boîtes de dialogue MFC, initialiser"
  - "boîtes de dialogue modales, initialiser"
  - "boîtes de dialogue non modales, initialiser"
  - "OnInitDialog (méthode)"
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Initialisation de la bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fois la boîte de dialogue et tous les contrôles créés mais juste avant la boîte de dialogue \(l'un des types\) s'affiche à l'écran, la fonction membre de [OnInitDialog](../Topic/CDialog::OnInitDialog.md) de l'objet du dialogue est appelée.  Pour une boîte de dialogue modale, ceci se produit lors de l'appel de `DoModal`.  Pour une boîte de dialogue non modales, `OnInitDialog` est appelée lorsque **Créer** est appelé.  Substituez généralement `OnInitDialog` pour initialiser les contrôles de la boîte de dialogue, tels que la définition initiale du texte d'une zone d'édition.  Vous devez appeler la fonction membre de `OnInitDialog` de la classe de base, `CDialog`, de la substitution de `OnInitDialog`.  
  
 Si vous souhaitez définir la couleur d'arrière\-plan de la boîte de dialogue \(et celle de toutes les autres boîtes de dialogue dans votre application\), consultez [Définir la couleur d'arrière\-plan de la boîte de dialogue](../mfc/setting-the-dialog-box’s-background-color.md).  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)