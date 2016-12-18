---
title: "sections (OpenMP) | Microsoft Docs"
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
  - "section"
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sections OpenMP directive"
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sections (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Reconnaît des sections de code à diviser parmi tous les threads.  
  
## Syntaxe  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## Notes  
 où,  
  
 `clause` \(facultatif\)  
 zéro clauses ou plus.  Consultez la section Notes pour une liste des clauses prises en charge par **sections**.  
  
## Notes  
 la directive de **sections** peut contenir zéro directives ou plus de **section** .  
  
 La directive de **sections** prend en charge les clauses suivantes OpenMP :  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 Si **parallèle** est également spécifié, `clause` peut être une clause acceptée par les directives de **parallèle** ou de **sections** , sauf `nowait`.  
  
 Pour plus d'informations, consultez [2.4.2 sections Construct](../../../parallel/openmp/2-4-2-sections-construct.md).  
  
## Exemple  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
  **Hello du thread 0**  
**Hello du thread 0**   
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)