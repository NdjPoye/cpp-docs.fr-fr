---
title: "omp_set_dynamic | Microsoft Docs"
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
  - "omp_set_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_dynamic OpenMP function"
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Indique que le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par le runtime.  
  
## Syntaxe  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## Notes  
 où,  
  
 `val`  
 Une valeur qui indique si le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par le runtime.  Si une valeur différente de zéro, le runtime peut ajuster le nombre de threads, si le zéro, le runtime ne s'ajuste pas dynamiquement le nombre de threads.  
  
## Notes  
 Le nombre de threads ne dépasse jamais la valeur définie par [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou par [OMP\_NUM\_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Utilisez [omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) pour afficher le paramètre actuel d' `omp_set_dynamic`.  
  
 Le paramètre pour `omp_set_dynamic` substitue le paramètre de la variable d'environnement [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) .  
  
 Pour plus d'informations, consultez [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## Exemple  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
  **1**  
**1**   
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)