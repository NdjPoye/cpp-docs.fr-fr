---
title: "Styles de barre de d&#233;filement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SBS_VERT"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN"
  - "SBS_LEFTALIGN"
  - "SBS_RIGHTALIGN"
  - "SBS_TOPALIGN"
  - "SBS_SIZEBOXTOPLEFTALIGN"
  - "SBS_BOTTOMALIGN"
  - "SBS_SIZEBOX"
  - "SBS_HORZ"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBS_BOTTOMALIGN (constante)"
  - "SBS_HORZ (constante)"
  - "SBS_LEFTALIGN (constante)"
  - "SBS_RIGHTALIGN (constante)"
  - "SBS_SIZEBOX (constante)"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN (constante)"
  - "SBS_SIZEBOXTOPLEFTALIGN (constante)"
  - "SBS_TOPALIGN (constante)"
  - "SBS_VERT (constante)"
  - "barres de défilement, styles"
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Styles de barre de d&#233;filement
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SBS\_BOTTOMALIGN** Utilisé avec le style **SBS\_HORZ**.  Le bord inférieur de la barre de défilement est aligné avec le bord inférieur du rectangle spécifié dans la méthode **Créer**.  La barre de défilement possède la hauteur par défaut pour les barres de défilement système.  
  
-   **SBS\_HORZ** Spécifie une barre de défilement horizontale.  Si ni le style de **SBS\_BOTTOMALIGN** ni de **SBS\_TOPALIGN** n'est spécifié, la barre de défilement possède la hauteur, la largeur, et la position spécifiées dans la méthode **Créer**.  
  
-   **SBS\_LEFTALIGN** Utilisé avec le style **SBS\_VERT**.  Le bord gauche de la barre de défilement est aligné avec le bord gauche du rectangle spécifié dans la méthode **Créer**.  La barre de défilement possède la largeur par défaut pour les barres de défilement système.  
  
-   **SBS\_RIGHTALIGN** Utilisé avec le style **SBS\_VERT**.  Le bord droit de la barre de défilement est aligné avec le bord droit du rectangle spécifié dans la méthode **Créer**.  La barre de défilement possède la largeur par défaut pour les barres de défilement système.  
  
-   **SBS\_SIZEBOX** Désigne une zone.  Si ni le style de **SBS\_SIZEBOXBOTTOMRIGHTALIGN** ni de **SBS\_SIZEBOXTOPLEFTALIGN** n'est spécifié, la taille de la boîte possède la hauteur, la largeur, et la position spécifiées dans la méthode **Créer**.  
  
-   **SBS\_SIZEBOXBOTTOMRIGHTALIGN** Utilisé avec le style de **SBS\_SIZEBOX**.  Le coin inférieur droit de la zone est aligné avec le coin inférieur droit du rectangle spécifié dans la méthode **Créer**.  La zone possède la taille par défaut pour les zones du système.  
  
-   **SBS\_SIZEBOXTOPLEFTALIGN** Utilisé avec le style **SBS\_SIZEBOX**.  Le coin supérieur gauche de la zone est aligné avec le coin supérieur gauche du rectangle spécifié dans la méthode **Créer**.  La zone possède la taille par défaut pour les zones du système.  
  
-   **SBS\_SIZEGRIP** De même que **SBS\_SIZEBOX**, mais avec un bord relevé.  
  
-   **SBS\_TOPALIGN** Utilisé avec le style **SBS\_HORZ**.  Le bord supérieur de la barre de défilement est aligné avec le bord supérieur du rectangle spécifié dans la méthode **Créer**.  La barre de défilement possède la hauteur par défaut pour les barres de défilement système.  
  
-   **SBS\_VERT** Représente une barre de défilement verticale.  Si ni le style de **SBS\_RIGHTALIGN** ni de **SBS\_LEFTALIGN** n'est spécifié, la barre de défilement possède la hauteur, la largeur, et la position spécifiées dans la méthode **Créer**.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../Topic/CScrollBar::Create.md)   
 [Scroll Bar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb787533)