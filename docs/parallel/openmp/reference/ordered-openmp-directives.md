---
title: "ordered (OpenMP Directives) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ordered"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered OpenMP directive"
ms.assetid: e1aa703e-d07d-4f6a-9b2a-f4f25203d850
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ordered (OpenMP Directives)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie ce code sous parallélisé de la boucle doit être exécuté comme une boucle séquentielle.  
  
## Syntaxe  
  
```  
#pragma omp ordered  
   structured-block  
```  
  
## Notes  
 La directive de **dimensionné** doit se situer dans l'étendue dynamique d'un élément de [for](../../../parallel/openmp/reference/for-openmp.md) ou de **parallèle pour** avec une clause de **dimensionné** .  
  
 La directive de **dimensionné** ne prend en charge aucune clauses OpenMP.  
  
 Pour plus d'informations, consultez [2.6.6 ordered Construct](../../../parallel/openmp/2-6-6-ordered-construct.md).  
  
## Exemple  
  
```  
// omp_ordered.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
static float a[1000], b[1000], c[1000];  
  
void test(int first, int last)   
{  
    #pragma omp for schedule(static) ordered  
    for (int i = first; i <= last; ++i) {  
        // Do something here.  
        if (i % 2)   
        {  
            #pragma omp ordered   
            printf_s("test() iteration %d\n", i);  
        }  
    }  
}  
  
void test2(int iter)   
{  
    #pragma omp ordered  
    printf_s("test2() iteration %d\n", iter);  
}  
  
int main( )   
{  
    int i;  
    #pragma omp parallel  
    {  
        test(1, 8);  
        #pragma omp for ordered  
        for (i = 0 ; i < 5 ; i++)  
            test2(i);  
    }  
}  
```  
  
  **testez \(\) l'itération 1**  
**itération 3 de test \(\)**  
**testez \(\) l'itération 5**  
**testez \(\) l'itération 7**  
**\(\) itération test2 0**  
**\(\) itération test2 1**  
**\(\) itération test2 2**  
**\(\) itération test2 3**  
**\(\) itération test2 4**   
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)