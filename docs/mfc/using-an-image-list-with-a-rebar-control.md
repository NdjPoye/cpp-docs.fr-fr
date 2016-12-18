---
title: "Utilisation d&#39;une liste d&#39;images avec un contr&#244;le rebar | Microsoft Docs"
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
  - "listes d'images (C++), rebar (contrôles)"
  - "rebar (contrôles), listes d'images"
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;une liste d&#39;images avec un contr&#244;le rebar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque bande rebar peut contenir, entre autres, une image d'une liste d'image associée.  La procédure suivante décrit les étapes nécessaires pour afficher une image dans une bande rebar.  
  
### Afficher des images dans une bande rebar  
  
1.  Attachez une liste des images à votre objet de contrôle rebar lors d'un appel à [SetImageList](../Topic/CReBarCtrl::SetImageList.md), en passant un pointeur vers une liste des images existante.  
  
2.  Modifiez la structure de **REBARBANDINFO** pour affecter une image à une bande rebar :  
  
    -   Définissez le membre **fMask** sur **RBBIM\_IMAGE**, en utilisant l'opérateur de bits OR pour inclure des balises supplémentaires comme nécessaire.  
  
    -   Définissez le membre `iImage` à l'index de liste des images de l'image à afficher.  
  
3.  Initialiser tous les membres de données restants, par exemple, la taille du texte, et le handle de la fenêtre enfant, avec les informations nécessaires.  
  
4.  Insérer une nouvelle bande \(avec l'image\) par un appel à [CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md), en passant la structure **REBARBANDINFO** .  
  
 Cet exemple suppose qu'un objet de liste d'images existant avec deux images a été attaché à l'objet de contrôle rebar \(`m_wndReBar`\).  Une nouvelle bande rebar \(définie par `rbi`\), contenant la première image, est ajoutée par un appel à `InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/CPP/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)