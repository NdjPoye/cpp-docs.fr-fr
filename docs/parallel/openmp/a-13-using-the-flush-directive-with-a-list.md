---
title: A.13 avec une liste à l’aide de la Directive de vidage | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6c9d0736-07c2-47b1-a216-5293f03b6397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9db8587f0f79b8f7b3fd367e633c83aa4b351058
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="a13---using-the-flush-directive-with-a-list"></a>A.13   Utilisation de la directive flush avec une liste
L’exemple suivant utilise la `flush` directive pour la synchronisation de point à point des objets spécifiques entre les paires de threads :  
  
```  
int   sync[NUMBER_OF_THREADS];  
float work[NUMBER_OF_THREADS];  
#pragma omp parallel private(iam,neighbor) shared(work,sync)  
{  
    iam = omp_get_thread_num();  
    sync[iam] = 0;  
    #pragma omp barrier  
  
    // Do computation into my portion of work array   
    work[iam] = ...;  
  
    //  Announce that I am done with my work  
    // The first flush ensures that my work is  
    // made visible before sync.  
    // The second flush ensures that sync is made visible.  
    #pragma omp flush(work)  
    sync[iam] = 1;  
    #pragma omp flush(sync)  
  
    // Wait for neighbor  
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;  
    while (sync[neighbor]==0)   
    {  
        #pragma omp flush(sync)  
    }  
  
    // Read neighbor's values of work array   
    ... = work[neighbor];  
}  
```