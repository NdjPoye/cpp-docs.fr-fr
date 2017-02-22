---
title: "omp_get_max_threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_max_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_max_threads OpenMP function"
ms.assetid: f47c3725-3e40-469f-8bc8-a1e47f264cc3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# omp_get_max_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Retourne un entier auquel est égal ou supérieur au nombre de threads qui sont disponibles si une région parallèle sans [num\_threads](../../../parallel/openmp/reference/num-threads.md) sont définies à ce stade de code.  
  
## Syntaxe  
  
```  
int omp_get_max_threads( )  
```  
  
## Notes  
 Pour plus d'informations, consultez [3.1.3 omp\_get\_max\_threads Function](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md).  
  
## Exemple  
  
```  
// omp_get_max_threads.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_num_threads(8);  
    printf_s("%d\n", omp_get_max_threads( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_max_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_max_threads( ));  
  
    #pragma omp parallel num_threads(3)  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_max_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_max_threads( ));  
}  
```  
  
  **8**  
**8**  
**8**  
**8**  
**8**   
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)