---
title: "3.2.2 omp_destroy_lock and omp_destroy_nest_lock Functions | Microsoft Docs"
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
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.2 omp_destroy_lock and omp_destroy_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions permettent de vérifier que l'aigu pour verrouiller *le verrou* variable est pas initialisé.  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Il n'est pas conforme pour appeler l'une ou l'autre de ces routines avec une variable de verrou qui n'est pas initialisée ou déverrouillée.