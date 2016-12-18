---
title: "for (OpenMP) | Microsoft Docs"
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
  - "for"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for OpenMP directive"
ms.assetid: 8b54e034-9db2-4c1a-a2b1-72e14e930506
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Permet de le travail effectué dans un pour l'intérieur de la boucle une région parallèle à diviser entre les threads.  
  
## Syntaxe  
  
```  
#pragma omp [parallel] for [clauses]  
   for_statement  
```  
  
## Notes  
 où,  
  
 `clause` \(facultatif\)  
 zéro clauses ou plus.  Consultez la section Notes pour une liste des clauses prises en charge par **pour**.  
  
 `for_statement`  
 Une boucle for.  Le comportement indéfini est générée si le code utilisateur dans la boucle modifie la variable d'index.  
  
## Notes  
 La directive de **pour** prend en charge les clauses suivantes OpenMP :  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [elle](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [dimensionné](../../../parallel/openmp/reference/ordered-openmp-directives.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [réduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [planification](../../../parallel/openmp/reference/schedule.md)  
  
 Si **parallèle** est également spécifié, `clause` peut être une clause acceptée par les directives de **parallèle** ou de **pour** , sauf **nowait**.  
  
 Pour plus d'informations, consultez [2.4.1 pour l'élément](../../../parallel/openmp/2-4-1-for-construct.md).  
  
## Exemple  
  
```  
// omp_for.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <math.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define NUM_START 1  
#define NUM_END 10  
  
int main() {  
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;  
   int nThreads = 0, nTmp = nStart + nEnd;  
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *   
                               unsigned(abs(nTmp))) / 2;  
   int nSumCalc = uTmp;  
  
   if (nTmp < 0)  
      nSumCalc = -nSumCalc;  
  
   omp_set_num_threads(NUM_THREADS);  
  
   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)  
   {  
      #pragma omp master  
      nThreads = omp_get_num_threads();  
  
      #pragma omp for  
      for (i=nStart; i<=nEnd; ++i) {  
            #pragma omp atomic  
            nSum += i;  
      }  
   }  
  
   if  (nThreads == NUM_THREADS) {  
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);  
      nRet = 0;  
   }  
   else {  
      printf_s("Expected %d OpenMP threads, but %d were used.\n",  
               NUM_THREADS, nThreads);  
      nRet = 1;  
   }  
  
   if (nSum != nSumCalc) {  
      printf_s("The sum of %d through %d should be %d, "  
               "but %d was reported!\n",  
               NUM_START, NUM_END, nSumCalc, nSum);  
      nRet = 1;  
   }  
   else  
      printf_s("The sum of %d through %d is %d\n",  
               NUM_START, NUM_END, nSum);  
}  
```  
  
  **4 Threads OpenMP ont été utilisés.  la somme de 1 à 10 est 55**    
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)