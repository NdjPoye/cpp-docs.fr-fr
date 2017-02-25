---
title: "atomic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atomic OpenMP directive"
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# atomic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

spécifie qu'un emplacement de mémoire qui sera mis à jour atomique.  
  
## Syntaxe  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### Paramètres  
 `expression`  
 L'instruction contenant l'emplacement mémoire lvalue dont vous souhaitez protéger contre plusieurs écrit.  Pour plus d'informations sur les formulaires d'expression légal, consultez la spécification d'OpenMP.  
  
## Notes  
 La directive d' `atomic` ne prend en charge aucune clauses OpenMP.  
  
 Pour plus d'informations, consultez [2.6.4 atomic Construct](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## Exemple  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
  **Nombre de threads : 10**   
## Voir aussi  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)