---
title: "OpenMP Environment Variables | Microsoft Docs"
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
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Environment Variables
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

fournit des liens vers des variables d'environnement utilisées dans l'API d'OpenMP.  
  
 L'implémentation de Visual C\+\+ du standard d'OpenMP inclut les variables d'environnement suivantes.  Ces variables d'environnement sont lues au démarrage du programme et les modifications apportées à leurs valeurs sont ignorées au moment de l'exécution \(par exemple, l'utilisation [\_putenv, \_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)\).  
  
|Variable d'environnement|Description|  
|------------------------------|-----------------|  
|[OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Spécifie si le runtime OpenMP peut ajuster le nombre de threads dans une région parallèle.|  
|[OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md)|spécifie si le parallélisme imbriqué est activé, à moins que le parallélisme imbriqué soit activé ou désactivé avec `omp_set_nested`.|  
|[OMP\_NUM\_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Définit le nombre maximal de threads dans une région parallèle, sauf si [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou [num\_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP\_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Modifie le comportement de la clause de [schedule](../../../parallel/openmp/reference/schedule.md) lorsque `schedule(runtime)` est spécifié dans une directive d' `for` ou d' `parallel for` .|  
  
## Voir aussi  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)