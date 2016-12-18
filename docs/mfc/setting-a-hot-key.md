---
title: "D&#233;finition d&#39;une touche d&#39;acc&#232;s rapide | Microsoft Docs"
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
  - "touches d'accès rapide (C++), touches d'accès rapide"
  - "CHotKeyCtrl (classe), définir une touche d'accès rapide"
  - "raccourcis clavier (C++), touches d'accès rapide"
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition d&#39;une touche d&#39;acc&#232;s rapide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre application peut utiliser les informations fournies par un contrôle de touche d'accès rapide \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) de deux manières :  
  
-   Installez une touche d'accès rapide d'agrégation pour activer une fenêtre de nonchild en envoyant un message [WM\_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) dans la fenêtre à vérifier.  
  
-   Installez une touche d'accès rapide spécifiques au thread lors de l'appel de la fonction Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## Voir aussi  
 [Utilisation de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)