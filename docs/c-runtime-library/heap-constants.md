---
title: "Constantes de tas | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_HEAPBADPTR"
  - "_HEAPEMPTY"
  - "_HEAPBADBEGIN"
  - "_HEAPOK"
  - "_HEAPBADNODE"
  - "_HEAPEND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HEAPBADBEGIN (constantes)"
  - "_HEAPBADNODE (constantes)"
  - "_HEAPBADPTR (constantes)"
  - "_HEAPEMPTY (constantes)"
  - "_HEAPEND (constantes)"
  - "_HEAPOK (constantes)"
  - "constantes de tas"
  - "HEAPBADBEGIN (constantes)"
  - "HEAPBADNODE (constantes)"
  - "HEAPBADPTR (constantes)"
  - "HEAPEMPTY (constantes)"
  - "HEAPEND (constantes)"
  - "HEAPOK (constantes)"
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Constantes de tas
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <malloc.h>  
  
```  
  
## Notes  
 Ces constantes retournent une veleur indiquant l'état du segment.  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_HEAPBADBEGIN`|Les informations d'en\-tête initiales sont introuvables ou sont valides.|  
|`_HEAPBADNODE`|Un nœud incorrect a été trouvé, ou le segment de mémoire est endommagé.|  
|`_HEAPBADPTR`|le champ de**\_pentry** de la structure de **\_HEAPINFO** ne contient pas le pointeur valide vers le segment \(routine `_heapwalk` uniquement\).|  
|`_HEAPEMPTY`|Le tas n'a pas été initialisé.|  
|`_HEAPEND`|La fin du segment a été atteinte correctement \(routine `_heapwalk` uniquement\).|  
|`_HEAPOK`|Le segment de mémoire est cohérent \(`_heapset` et les routines `_heapchk` uniquement\).  Aucune erreur jusqu'à présent ; la structure de **\_HEAPINFO** contient des informations sur l'entrée suivante \(routine d'`_heapwalk` uniquement\).|  
  
## Voir aussi  
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)