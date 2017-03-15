---
title: "Utilisation d&#39;un contr&#244;le commun en tant que fen&#234;tre enfant | Microsoft Docs"
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
  - "fenêtres enfants, contrôles communs comme"
  - "contrôles communs (C++), fenêtres enfants"
  - "contrôles (MFC), utiliser comme fenêtres enfants"
  - "fenêtres (C++), contrôles communs comme"
  - "contrôles Windows communs (C++), fenêtres enfants"
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation d&#39;un contr&#244;le commun en tant que fen&#234;tre enfant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles communs Windows peuvent être utilisés comme fenêtre enfant d'un autre fenêtre.  La procédure suivante explique comment créer un contrôle commun dynamiquement et ensuite travailler avec.  
  
### Utiliser un contrôle commun en tant que fenêtre enfant  
  
1.  Définissez le contrôle de la classe ou le gestionnaire associée.  
  
2.  Utilisez la substitution de contrôler la méthode [CWnd::Create](../Topic/CWnd::Create.md) pour créer le contrôle Windows.  
  
3.  Une fois le contrôle créé \(dès que le gestionnaire `OnCreate` si vous sous\-classez le contrôle\), vous pouvez manipuler le contrôle à l'aide des fonctions membres.  Consultez les descriptions des contrôles sur [Contrôles](../mfc/controls-mfc.md) pour plus d'informations sur les méthodes.  
  
4.  Lorsque vous avez terminé avec le contrôle, utilisez [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md) à détruire le contrôle.  
  
## Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)