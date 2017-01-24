---
title: "omp_get_wtime | Microsoft Docs"
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
  - "omp_get_wtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_wtime OpenMP function"
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_wtime
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Retourne une valeur en secondes du temps écoulé d'un certain point.  
  
## Syntaxe  
  
```  
double omp_get_wtime( );  
```  
  
## Valeur de retour  
 Retourne une valeur en secondes du temps écoulé d'un certain point arbitraire, mais cohérent.  
  
## Notes  
 Ce point reste cohérent pendant l'exécution du programme, qui effectuent des comparaisons suivantes possibles.  
  
 Pour plus d'informations, consultez [3.3.1 omp\_get\_wtime Function](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).  
  
## Exemple  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
  **début \= 594255,3671159324**  
**fin \= 594256,3664474116**  
**comparaison \= 0,9993314791936427**  
**wtick \= 2.793651148400146e\-007**  
**1\/wtick \= 3579545**   
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)