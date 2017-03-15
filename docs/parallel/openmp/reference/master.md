---
title: "master | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "master"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "master OpenMP directive"
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# master
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie que seul le principal threadshould exécutent une section du programme.  
  
## Syntaxe  
  
```  
#pragma omp master  
{  
   code_block  
}  
```  
  
## Notes  
 La directive de **page maître** ne prend en charge aucune clauses OpenMP.  
  
 La directive de [single](../../../parallel/openmp/reference/single.md) vous permet de spécifier qu'une section de code doit être exécutée sur un thread unique, pas nécessairement le thread principal.  
  
 Pour plus d'informations, consultez [2.6.1 master Construct](../../../parallel/openmp/2-6-1-master-construct.md).  
  
## Exemple  
  
```  
// omp_master.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
  
int main( )   
{  
    int a[5], i;  
  
    #pragma omp parallel  
    {  
        // Perform some computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] = i * i;  
  
        // Print intermediate results.  
        #pragma omp master  
            for (i = 0; i < 5; i++)  
                printf_s("a[%d] = %d\n", i, a[i]);  
  
        // Wait.  
        #pragma omp barrier  
  
        // Continue with the computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] += i;  
    }  
}  
```  
  
  **une fonction \[0\] \= 0**  
**une fonction \[1\] \= 1**  
**une fonction \[2\] \= 4**  
**une fonction \[3\] \= 9**  
**une fonction \[4\] \= 16**   
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)