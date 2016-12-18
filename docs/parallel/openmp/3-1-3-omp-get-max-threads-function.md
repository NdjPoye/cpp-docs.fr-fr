---
title: "3.1.3 omp_get_max_threads Function | Microsoft Docs"
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
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.3 omp_get_max_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' **omp\_get\_max\_threads** retourne un entier qui est obligatoirement au moins aussi important que le nombre de threads qui sont utilisés pour former une équipe si une région parallèle sans clause de **num\_threads** doivent être générées à ce stade de code.  Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 Ce qui suit exprime une limite inférieure à la valeur d' **omp\_get\_max\_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 Notez que si une région parallèle suivante utilise la clause de **num\_threads** pour demander un nombre spécifique de threads, la garantie sur la limite inférieure du résultat d' **omp\_get\_max\_threads** aucun longs contient.  
  
 La valeur de retour de la fonction d' **omp\_get\_max\_threads** peut être utilisée pour allouer dynamiquement le stockage suffisant pour tous les threads de l'équipe formée à la région parallèle suivante.  
  
## Références croisées :  
  
-   la fonction d'**omp\_get\_num\_threads** , consultez [section 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) à la page 37.  
  
-   la fonction d'**omp\_set\_num\_threads** , consultez [section 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) à la page 36.  
  
-   la fonction d'**omp\_set\_dynamic** , consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.  
  
-   la clause de**num\_threads** , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.