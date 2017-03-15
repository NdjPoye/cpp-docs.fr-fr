---
title: "A.5   Using the critical Directive | Microsoft Docs"
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
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.5   Using the critical Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant inclut plusieurs directives d' `critical` \([section 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) à la page 18\).  L'exemple illustre un modèle de mise en file d'attente en exécutant une tâche est retirée et utilisée de la file d'attente.  Afin de se protéger contre plusieurs threads retirant la même tâche, l'opération retirante de la file d'attente doit se trouver dans une section d' `critical` .  Étant donné que les deux files d'attente dans cet exemple sont indépendantes, elles sont protégées par les directives d' `critical` avec des noms, *l'axe* x et *l'axe y*différents.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```