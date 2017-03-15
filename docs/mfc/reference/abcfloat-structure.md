---
title: "ABCFLOAT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ABCFLOAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABCFLOAT (structure)"
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ABCFLOAT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `ABCFLOAT` contient la largeur de A, B, et C d'un caractère de la police.  
  
## Syntaxe  
  
```  
  
      typedef struct _ABCFLOAT { /* abcf */  
   FLOAT abcfA;  
   FLOAT abcfB;  
   FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### Paramètres  
 *abcfA*  
 Spécifie l'espacement A du caractère.  L'espacement A correspond à la distance à ajouter à la position actuelle avant d'ajouter le glyphe du caractère.  
  
 *abcfB*  
 Spécifie l'espacement B du caractère.  L'espace B est la largeur de la partie tracée du glyphe du caractère.  
  
 *abcfC*  
 Spécifie l'espacement C du caractère.  L'espace C correspond à la distance à ajouter à la position actuelle de fournir les espaces à droite du glyphe du caractère.  
  
## Notes  
 Les largeurs de A, B, et C sont mesurées suivant la ligne de la police.  L'incrément de caractères \(largeur totale\) d'un caractère est la somme des espaces A, B et C.  Les espaces A ou C peuvent être négatifs pour indiquer les dépassements.  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)