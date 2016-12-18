---
title: "A.10   Specifying Sequential Ordering | Microsoft Docs"
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
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.10   Specifying Sequential Ordering
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les sections ordonnées \([section 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) à la page 22\) sont utiles pour classer séquentiellement la sortie du travail exécuté en parallèle.  Le programme suivant imprime les index dans un ordre séquentiel :  
  
```  
#pragma omp for ordered schedule(dynamic)  
    for (i=lb; i<ub; i+=st)  
        work(i);  
void work(int k)  
{  
    #pragma omp ordered  
        printf_s(" %d", k);  
}  
```