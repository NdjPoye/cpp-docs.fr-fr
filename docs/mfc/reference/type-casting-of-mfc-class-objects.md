---
title: "Cast de type des objets de classe MFC | Microsoft Docs"
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
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "caster des types"
  - "macros, caster des pointeurs"
  - "macros, types (cast)"
  - "pointeurs, types (cast)"
  - "casts de type"
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cast de type des objets de classe MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les macros de conversion de types permettent de convertir un pointeur attribué à un pointeur qui pointe vers un objet de classe spécifique, avec ou sans vérification que la conversion soit légale.  
  
 Le tableau suivant répertorie les macros de conversion de type MFC.  
  
### Macros qui convertissent des pointeurs sur les objets de classe MFC  
  
|||  
|-|-|  
|[DYNAMIC\_DOWNCAST](../Topic/DYNAMIC_DOWNCAST.md)|Convertit un pointeur vers un pointeur sur un objet de classe lors de la vérification pour déterminer si la conversion est légale.|  
|[STATIC\_DOWNCAST](../Topic/STATIC_DOWNCAST.md)|Convertit un pointeur vers un objet d'une classe dans un pointeur de type associé.  Dans une version de débogage, met **ASSERT** si l'objet n'est pas un « type » du type cible.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)