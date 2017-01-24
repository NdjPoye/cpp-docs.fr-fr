---
title: "OpenMP Functions | Microsoft Docs"
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
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Functions
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Fournit des liens vers les fonctions utilisées dans l'API d'OpenMP.  
  
 L'implémentation de Visual C\+\+ du standard d'OpenMP inclut les fonctionnalités suivantes.  
  
|Fonction|Description|  
|--------------|-----------------|  
|[omp\_destroy\_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Uninitializes un verrou.|  
|[omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Uninitializes un verrou empilable.|  
|[omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Retourne une valeur qui indique si le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par le runtime.|  
|[omp\_get\_max\_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Retourne un entier auquel est égal ou supérieur au nombre de threads qui sont disponibles si une région parallèle sans [num\_threads](../../../parallel/openmp/reference/num-threads.md) sont définies à ce stade de code.|  
|[omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md)|Retourne une valeur qui indique si le parallélisme imbriqué est activé.|  
|[omp\_get\_num\_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|Retourne le nombre de processeurs disponibles lorsque la fonction est appelée.|  
|[omp\_get\_num\_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|Retourne le nombre de threads dans une région parallèle.|  
|[omp\_get\_thread\_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Retourne le numéro du thread s'exécutant dans son équipe de thread.|  
|[omp\_get\_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|Retourne le nombre de secondes entre les battements d'horloge du processeur.|  
|[omp\_get\_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Retourne une valeur en secondes du temps écoulé d'un certain point.|  
|[omp\_in\_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Retourne une valeur différente de zéro si elle est appelée d'une région parallèle.|  
|[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)|initialise un verrou simple.|  
|[omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|initialise un verrou.|  
|[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Indique que le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par le runtime.|  
|[omp\_set\_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Les blocs thread l'exécution jusqu'à ce qu'un verrou soit disponible.|  
|[omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Les blocs thread l'exécution jusqu'à ce qu'un verrou soit disponible.|  
|[omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md)|Permet un imbriqué le parallélisme.|  
|[omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|Définit le nombre de threads dans les régions parallèles suivantes, sauf si une clause de [num\_threads](../../../parallel/openmp/reference/num-threads.md) .|  
|[omp\_test\_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Essaie de définir un verrou mais ne bloque pas l'exécution des threads.|  
|[omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Essaie de définir un verrou empilable mais ne bloque pas l'exécution des threads.|  
|[omp\_unset\_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|libère un verrou.|  
|[omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|libère un verrou empilable.|  
  
## Voir aussi  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)