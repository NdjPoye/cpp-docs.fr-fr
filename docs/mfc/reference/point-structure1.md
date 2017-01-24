---
title: "POINT, structure | Microsoft Docs"
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
  - "POINT"
  - "LPPOINT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPPOINT (structure)"
  - "POINT (structure)"
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# POINT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure **POINT** définit les coordonnées X*\-* et Y d'un point.  
  
## Syntaxe  
  
```  
  
      typedef struct tagPOINT {  
   LONG x;  
   LONG y;  
} POINT;  
```  
  
#### Paramètres  
 *x*  
 Spécifie l'abscisse d'un point.  
  
 *y*  
 Spécifie l'ordonnée d'un point.  
  
## Exemple  
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/CPP/point-structure1_1.cpp)]  
  
## Configuration requise  
 **Header:** windef.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint Class](../../atl-mfc-shared/reference/cpoint-class.md)