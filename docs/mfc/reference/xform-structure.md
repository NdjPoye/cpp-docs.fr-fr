---
title: "XFORM, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "XFORM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XFORM (structure)"
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# XFORM, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `XFORM` se présente sous la forme suivante :  
  
## Syntaxe  
  
```  
  
      typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## Notes  
 La structure `XFORM` spécifie une transformation d'espace de texte à espace de page.  Les membres **eDx** et **eDy** spécifient les composants horizontaux et verticaux de la translation, respectivement.  Le tableau suivant illustre comment les autres membres sont utilisés, selon l'opération :  
  
|Opération|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Cosinus de l'angle de rotation|Sinus de l'angle de rotation|Sinus négatif d'angle de rotation|Cosinus de l'angle de rotation|  
|**Mise à l'échelle**|Composant horizontal de mise à l'échelle|Nothing|Nothing|Composant vertical de mise à l'échelle|  
|**Inclinaison**|Nothing|Constante de proportionnalité horizontale|Constante verticale de proportionnalité|Nothing|  
|**Réflexion**|Composant horizontal de réflexion|Nothing|Nothing|Composant vertical de réflexion|  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../Topic/CRgn::CreateFromData.md)