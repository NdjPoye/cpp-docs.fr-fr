---
title: "ABC, structure | Microsoft Docs"
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
  - "ABC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABC (structure)"
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ABC, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure **ABC** contient la largeur d'un caractère dans une police TrueType.  
  
## Syntaxe  
  
```  
  
      typedef struct _ABC { /* abc */  
   int abcA;  
   UINT abcB;  
   int abcC;  
} ABC;  
```  
  
#### Paramètres  
 *abcA*  
 Spécifie l'espacement A du caractère.  L'espacement A correspond à la distance à ajouter à la position actuelle avant d'ajouter le glyphe du caractère.  
  
 *abcB*  
 Spécifie l'espacement B du caractère.  L'espace B est la largeur de la partie tracée du glyphe du caractère.  
  
 *abcC*  
 Spécifie l'espacement C du caractère.  L'espace C correspond à la distance à ajouter à la position actuelle de fournir les espaces à droite du glyphe du caractère.  
  
## Notes  
 La largeur totale d'un caractère est la somme des espaces A, B, et C.  Les espaces A ou C peuvent être négatifs pour indiquer les dépassements.  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)