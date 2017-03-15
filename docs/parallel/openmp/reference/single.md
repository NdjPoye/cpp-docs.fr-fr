---
title: "single | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Single"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single OpenMP directive"
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# single
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Vous permet de spécifier qu'une section de code doit être exécutée sur un thread unique, pas nécessairement le thread principal.  
  
## Syntaxe  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### Paramètres  
 `clause` \(facultatif\)  
 zéro clauses ou plus.  Consultez la section Notes pour une liste des clauses prises en charge par **unique**.  
  
## Notes  
 La directive d' **unique** prend en charge les clauses suivantes OpenMP :  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 La directive de [master](../../../parallel/openmp/reference/master.md) vous permet de spécifier qu'une section de code doit être exécutée uniquement sur le thread principal.  
  
 Pour plus d'informations, consultez [2.4.3 single Construct](../../../parallel/openmp/2-4-3-single-construct.md).  
  
## Exemple  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
  **entrée de lecture**  
**résultats de calcul**  
**résultats de calcul**  
**sortie d'écriture**   
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)