---
title: "A.12   Using the atomic Directive | Microsoft Docs"
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
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.12   Using the atomic Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant évite les conditions de concurrence critique \(mises à jour simultanée d'un élément *de x* par plusieurs threads\) à l'aide de la directive d' `atomic` \([section 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) à la page 19\) :  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 L'avantage d'utiliser la directive d' `atomic` dans cet exemple est qu'elle permet aux mises à jour de deux éléments différents x de se produire en parallèle.  Si une directive d' `critical` \([section 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) à la page 18\) était utilisée à la place, toutes les mises à jour des éléments *de x* seraient exécutés séquentiel \(mais pas dans toute commande garantie\).  
  
 Notez que la directive d' `atomic` s'applique uniquement à l'instruction C ou C\+\+ qui suit immédiatement elle.  Par conséquent, les éléments *de y* ne sont pas mis à jour atomique dans cet exemple.