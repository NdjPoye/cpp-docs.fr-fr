---
title: "3.1.2 omp_get_num_threads Function | Microsoft Docs"
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
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.2 omp_get_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' **omp\_get\_num\_threads** retourne le nombre de threads actuellement dans l'équipe qui exécute la région parallèle dont elle est appelée.  Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 La clause de **num\_threads** , la fonction d' **omp\_set\_num\_threads** , et le contrôle de variable d'environnement **OMP\_NUM\_THREADS** le nombre de threads dans une équipe.  
  
 Si le nombre de threads n'a pas été explicitement défini par l'utilisateur, la valeur par défaut implémentation\-est définie.  Cette fonction se lie à la directive de **parallèle** englobante la plus proche.  En cas de appel d'une partie série d'un programme, ou d'une région parallèle imbriquée qui est sérialisée, retourne 1. de cette fonction.  
  
## Références croisées :  
  
-   La variable d'environnement**OMP\_NUM\_THREADS** , consultez [section 4,2](../../parallel/openmp/4-2-omp-num-threads.md) à la page 48.  
  
-   la clause de**num\_threads** , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.  
  
-   l'élément de**parallèle** , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.