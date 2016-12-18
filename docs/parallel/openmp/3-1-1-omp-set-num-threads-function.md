---
title: "3.1.1 omp_set_num_threads Function | Microsoft Docs"
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
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.1 omp_set_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' `omp_set_num_threads` définit le nombre par défaut de threads à utiliser pour les zones parallèles suivantes qui ne spécifient pas de clause d' `num_threads` .  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 La valeur *de num\_threads* de paramètre doit être un entier positif.  Son effet dépend au moment si le réglage dynamique du nombre de threads est activé.  Pour un ensemble de règles sur l'interaction entre la fonction d' `omp_set_num_threads` et la modification dynamique des threads, consultez la section 2,3 à la page 8.  
  
 Cette fonction a les effets décrits ci\-dessus en cas de appel d'une partie du programme où la fonction d' `omp_in_parallel` retourne zéro.  Si elle est appelée dans une partie du programme où la fonction d' `omp_in_parallel` retourne une valeur différente de zéro, le comportement de cette fonction n'est pas défini.  
  
 Cet appel est prioritaire sur la variable d'environnement `OMP_NUM_THREADS` .  La valeur par défaut du nombre de threads, qui peuvent être générés en appelant `omp_set_num_threads` ou en définissant la variable d'environnement `OMP_NUM_THREADS` , peut être substituée explicitement sur une directive unique de **parallèle** en spécifiant la clause d' `num_threads` .  
  
## Références croisées :  
  
-   la fonction d'`omp_set_dynamic` , consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.  
  
-   la fonction d'`omp_get_dynamic` , consultez [section 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) à la page 40.  
  
-   la variable d'environnement`OMP_NUM_THREADS` , consultez [section 4,2](../../parallel/openmp/4-2-omp-num-threads.md) à la page 48, et la section 2,3 à la page 8.  
  
-   la clause d'`num_threads` , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8