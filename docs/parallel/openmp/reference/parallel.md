---
title: "parallel | Microsoft Docs"
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
  - "parallel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parallel OpenMP directive"
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# parallel
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Définit une zone parallèle, qui est le code qui sera exécuté par plusieurs threads en parallèle.  
  
## Syntaxe  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## Notes  
 où,  
  
 `clause` \(facultatif\)  
 zéro clauses ou plus.  Consultez la section Notes pour une liste des clauses prises en charge par **parallèle**.  
  
## Notes  
 La directive de **parallèle** prend en charge les clauses suivantes OpenMP :  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num\_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **parallèle** peut également être utilisé avec les directives de [sections](../../../parallel/openmp/reference/sections-openmp.md) et de [for](../../../parallel/openmp/reference/for-openmp.md) .  
  
 Pour plus d'informations, consultez [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Exemple  
 L'exemple suivant indique comment définir le nombre de threads et de définir une région parallèle.  Par défaut, le nombre de threads est égal au nombre de processeurs logiques sur l'ordinateur.  Par exemple, si vous avez un ordinateur avec un processeur physique équipée d'hyperthreading activé, il possède deux processeurs logiques et, par conséquent, plusieurs threads.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
  **Hello du thread 0**  
**Hello du thread 1**  
**Hello du thread 2**  
**Hello du thread 3**   
## Commentaire  
 Notez que l'ordre de sortie peut varier sur des ordinateurs différents.  
  
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)