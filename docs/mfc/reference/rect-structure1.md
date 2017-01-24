---
title: "RECT, structure | Microsoft Docs"
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
  - "LPRECT"
  - "RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPRECT (structure)"
  - "RECT (structure)"
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RECT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `RECT` définit les coordonnées supérieure gauche et des angles inférieur droit d'un rectangle.  
  
## Syntaxe  
  
```  
  
      typedef struct tagRECT {   
   LONG left;  
   LONG top;  
   LONG right;  
   LONG bottom;  
} RECT;  
```  
  
## Membres  
 `left`  
 Specifie les coordonnée x du coin supérieur gauche d'un rectangle.  
  
 `top`  
 Specifie les coordonnée y du coin supérieur gauche d'un rectangle.  
  
 `right`  
 Specifie les coordonnée x du coin supérieur droit d'un rectangle.  
  
 `bottom`  
 Specifie les coordonnée y du coin inférieur droit d'un rectangle.  
  
## Exemple  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/CPP/rect-structure1_1.cpp)]  
  
## Configuration requise  
 **Header:** windef.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)