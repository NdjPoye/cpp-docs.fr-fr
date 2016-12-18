---
title: "omp_test_lock | Microsoft Docs"
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
  - "omp_test_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_lock OpenMP function"
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Essaie de définir un verrou mais ne bloque pas l'exécution des threads.  
  
## Syntaxe  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## Notes  
 où,  
  
 `lock`  
 une variable du type [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) qui a été initialisé avec [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## Notes  
 Pour plus d'informations, consultez [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).  
  
## Exemple  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
  **Thread 1 \- simple\_lock interrompu**  
**thread 1 \- simple\_lock finale**  
**thread 0 \- pour acquérir le simple\_lock**  
**thread 3 \- pour acquérir le simple\_lock**  
**thread 0 \- pour acquérir le simple\_lock**  
**thread 3 \- pour acquérir le simple\_lock**  
**Thread 2 \- simple\_lock interrompu**  
**thread 0 \- pour acquérir le simple\_lock**  
**thread 3 \- pour acquérir le simple\_lock**  
**thread 0 \- pour acquérir le simple\_lock**  
**thread 3 \- pour acquérir le simple\_lock**  
**thread 2 \- simple\_lock finale**  
**thread 0 \- pour acquérir le simple\_lock**  
**thread 3 \- pour acquérir le simple\_lock**  
**Thread 0 \- simple\_lock interrompu**  
**thread 3 \- pour acquérir le simple\_lock**  
**thread 0 \- simple\_lock finale**  
**thread 3 \- pour acquérir le simple\_lock**  
**Thread 3 \- simple\_lock interrompu**  
**thread 3 \- simple\_lock finale**   
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)