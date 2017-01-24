---
title: "&#201;l&#233;ments de rappel et masque de rappel | Microsoft Docs"
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
  - "éléments de rappel dans la classe CListCtrl"
  - "CListCtrl (classe), élément de rappel et masque de rappel"
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;l&#233;ments de rappel et masque de rappel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour chacun de ses éléments, un contrôle list VIEW enregistre généralement le texte d'étiquette, l'index de liste des images des icônes de l'élément, et un jeu d'indicateurs de bits pour l'état de l'élément.  Vous pouvez définir des éléments comme éléments de rappel, qui sont utiles si votre application stocke déjà une partie des informations pour un élément.  
  
 Vous définissez un élément en tant qu'élément de rappel en spécifiant les valeurs appropriées pour les membres `pszText` et `iImage` de la structure de **LV\_ITEM** \(voir [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)\).  Si l'application gère l'élément ou le texte du sous\-élément, spécifiez la valeur de **LPSTR\_TEXTCALLBACK** du membre `pszText`.  Si l'application gère l'icône de l'élément, spécifiez la valeur de **I\_IMAGECALLBACK** du membre `iImage`.  
  
 En plus de définir les éléments de rappel, vous pouvez également modifier le masque de rappel du contrôle.  Ce filtre est un ensemble d'indicateurs de bits qui spécifient les états d'éléments pour lesquels l'application, plutôt que le contrôle, stocke les données actuelles.  Le masque de rappel s'applique à tous les éléments de commande, contrairement à la désignation de rappel d'élément, qui s'applique à un élément spécifique.  Le masque de rappel est nulle par défaut, ce qui signifie que le contrôle suit tous les états d'élément.  Pour modifier ce comportement par défaut, initialisez le masque à n'importe quelle combinaison de valeurs suivantes :  
  
-   `LVIS_CUT` l'élément est marqué pour un couper et coller.  
  
-   `LVIS_DROPHILITED` l'élément est mis en surbrillance comme cible pour un glisser\-déplacer.  
  
-   `LVIS_FOCUSED` l'élément a l'attention.  
  
-   `LVIS_SELECTED` L'élément est sélectionné.  
  
-   **LVIS\_OVERLAYMASK** l'application enregistre l'index de liste des images de chevauchement actuel pour chaque élément.  
  
-   **LVIS\_STATEIMAGEMASK** l'application enregistre l'index de liste des images d'état actuel pour chaque élément.  
  
 Pour les informations sur la récupération et la définition de ce masque, consultez [CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md) et [CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md).  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)