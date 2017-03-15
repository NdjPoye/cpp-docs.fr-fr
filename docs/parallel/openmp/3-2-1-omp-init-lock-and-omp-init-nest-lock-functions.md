---
title: "3.2.1 omp_init_lock and omp_init_nest_lock Functions | Microsoft Docs"
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.1 omp_init_lock and omp_init_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions fournissent les seuls moyen d'initialiser un verrou.  Chaque fonction initialise le verrou associé au *verrouillage* du paramètre pour une utilisation dans les appels suivants.  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 L'état initial est déverrouillé \(autrement dit, aucun thread ne possède le verrou\).  pour un verrou empilable, le nombre initial d'imbrication est zéro.  Il n'est pas conforme pour appeler l'une ou l'autre de ces routines avec une variable de verrou qui a déjà été initialisée.