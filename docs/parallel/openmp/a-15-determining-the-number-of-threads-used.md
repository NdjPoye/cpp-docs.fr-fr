---
title: "A.15   Determining the Number of Threads Used | Microsoft Docs"
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
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.15   Determining the Number of Threads Used
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prenons l'exemple incorrect suivant \(pour [section 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) à la page 37\) :  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 L'appel d' `omp_get_num_threads()` retourne 1 dans la section série de *le* code, le *NP* sera toujours égale à 1 dans l'exemple précédent.  Pour déterminer le nombre de threads qui seront déployés pour la zone parallèle, l'appel doit être à l'intérieur de la région parallèle.  
  
 L'exemple suivant montre comment réécrire ce programme sans inclure une requête pour le nombre de threads :  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```