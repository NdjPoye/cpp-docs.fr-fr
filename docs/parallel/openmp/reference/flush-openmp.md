---
title: "flush (OpenMP) | Microsoft Docs"
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
  - "Flush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flush OpenMP directive"
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# flush (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie que tous les threads ont le même point de vue de la mémoire pour tous les objets partagés.  
  
## Syntaxe  
  
```  
#pragma omp flush [(var)]  
```  
  
## Notes  
 où,  
  
 `var` \(facultatif\)  
 Une liste avec la virgule comme séparateur des variables qui représentent des objets vous souhaitez synchroniser.  Si `var` n'est pas spécifié, toute la mémoire doit être vidée.  
  
## Notes  
 La directive de **vide** ne prend en charge aucune clauses OpenMP.  
  
 Pour plus d'informations, consultez [2.6.5 flush Directive](../../../parallel/openmp/2-6-5-flush-directive.md).  
  
## Exemple  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
  **thread 0 : données de lecture**  
**thread 1 : données de processus**  
**données \= 2**   
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)