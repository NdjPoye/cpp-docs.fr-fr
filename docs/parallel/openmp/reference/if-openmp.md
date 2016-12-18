---
title: "if (OpenMP) | Microsoft Docs"
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
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "if OpenMP clause"
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# if (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie si une boucle doit être exécutée en parallèle ou dans l'interface série.  
  
## Syntaxe  
  
```  
if(expression)  
```  
  
## Notes  
 où,  
  
 `expression`  
 Une expression complète qui, si elle prend la valeur true \(différent de zéro\), fait pour exécuter du code dans une région parallèle en parallèle.  Si l'expression a la valeur false \(zéro\), la région parallèle est exécutée dans l'interface série \(par un thread unique\).  
  
## Notes  
 `if` s'applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d'informations, consultez [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Exemple  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
  **\= 0 val, sérialisé**  
**\= 2 val, parallélisé avec 2 threads**   
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)