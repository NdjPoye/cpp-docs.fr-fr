---
title: "MINMAXINFO, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MINMAXINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MINMAXINFO (structure)"
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MINMAXINFO, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure de `MINMAXINFO` contient des informations sur la taille et la position maximisée de la fenêtre et les valeur minimale et maximale de la taille de suivi.  
  
## Syntaxe  
  
```  
  
      typedef struct tagMINMAXINFO {  
   POINT ptReserved;  
   POINT ptMaxSize;  
   POINT ptMaxPosition;  
   POINT ptMinTrackSize;  
   POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### Paramètres  
 *ptReserved*  
 Réservé à une utilisation interne.  
  
 *ptMaxSize*  
 Spécifie la largeur maximisée \(point.x\) et la hauteur maximisée \(point.y\) de la fenêtre.  
  
 `ptMaxPosition`  
 Spécifie la position du côté gauche de la fenêtre maximisée \(point.x\) et la position supérieure de la fenêtre maximisée \(point.y\).  
  
 *ptMinTrackSize*  
 Spécifie la largeur minimale de suivi \(point.x\) et la hauteur minimale de suivi \(point.y\) de la fenêtre.  
  
 *ptMaxTrackSize*  
 Spécifie la largeur maximale de suivi \(point.x\) et la hauteur maximale de suivi \(point.y\) de la fenêtre.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)