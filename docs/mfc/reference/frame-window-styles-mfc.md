---
title: "Styles de fen&#234;tre frame (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FWS_ADDTOTITLE"
  - "FWS_SNAPTOBARS"
  - "FWS_PREFIXTITLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres frame, styles"
  - "FWS_ADDTOTITLE (constante)"
  - "FWS_PREFIXTITLE (constante)"
  - "FWS_SNAPTOBARS (constante)"
  - "styles, fenêtres"
ms.assetid: d21f270e-a088-4962-a2ae-8c03334b5a06
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Styles de fen&#234;tre frame (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **FWS\_ADDTOTITLE** spécifie les informations à ajouter à la fin d'un titre de la fenêtre cadre.  Par exemple, « Microsoft dessin \- dessiner dans Document1 ».  Vous pouvez spécifier les chaînes affichées dans l'onglet de chaînes modèles dans le document de l'Application.  Si vous devez désactiver cette option, substituez la fonction membre de `CWnd::PreCreateWindow`.  
  
-   **FWS\_PREFIXTITLE** indique le nom du document avant le nom de l'application dans un titre de la fenêtre cadre.  Par exemple, « Document \- WordPad ».  Vous pouvez spécifier les chaînes affichées dans l'onglet de chaînes modèles dans le document de l'Application.  Si vous devez désactiver cette option, substituez la fonction membre de `CWnd::PreCreateWindow`.  
  
-   Classement par taille de contrôle de**FWS\_SNAPTOBARS** de la fenêtre cadre qui joint une barre de contrôles lorsque cela est dans une fenêtre flottante et non ancrée à une fenêtre du cadre.  Ce style dimensionne la fenêtre pour qu'elle accueille la barre de contrôle.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)