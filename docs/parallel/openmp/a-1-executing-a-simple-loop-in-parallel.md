---
title: "A.1   Executing a Simple Loop in Parallel | Microsoft Docs"
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
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.1   Executing a Simple Loop in Parallel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant indique comment paralléliser une boucle simple à l'aide de la directive d' `parallel for` \([section 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) à la page 16\).  La variable d'itération de boucle est privée par défaut, il n'est pas nécessaire de la spécifier explicitement dans une clause privée.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```