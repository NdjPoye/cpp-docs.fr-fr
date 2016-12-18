---
title: "num_threads | Microsoft Docs"
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
  - "num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_threads OpenMP clause"
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Définit le nombre de threads dans une équipe de thread.  
  
## Syntaxe  
  
```  
num_threads(num)  
```  
  
## Notes  
 où,  
  
 `num`  
 Le nombre de threads  
  
## Notes  
 La clause d' `num_threads` a les mêmes fonctionnalités que la fonction d' [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) .  
  
 `num_threads` s'applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d'informations, consultez [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Exemple  
 Consultez [parallel](../../../parallel/openmp/reference/parallel.md) pour obtenir un exemple de clause d'utilisation `num_threads` .  
  
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)