---
title: "omp_set_num_threads | Microsoft Docs"
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
  - "omp_set_num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_num_threads OpenMP function"
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Définit le nombre de threads dans les régions parallèles suivantes, sauf si une clause de [num\_threads](../../../parallel/openmp/reference/num-threads.md) .  
  
## Syntaxe  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## Notes  
 où,  
  
 `num_threads`  
 Le nombre de threads dans une région parallèle.  
  
## Notes  
 Pour plus d'informations, consultez [3.1.1 omp\_set\_num\_threads Function](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).  
  
## Exemple  
 Consultez l' [omp\_get\_num\_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) pour un exemple d'utilisation `omp_set_num_threads`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)