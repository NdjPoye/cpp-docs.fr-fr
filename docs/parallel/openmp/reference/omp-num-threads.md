---
title: "OMP_NUM_THREADS | Microsoft Docs"
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
  - "OMP_NUM_THREADS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NUM_THREADS OpenMP environment variable"
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Définit le nombre maximal de threads dans une région parallèle, sauf si [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou [num\_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## Syntaxe  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## Notes  
 où,  
  
 `num`  
 Le nombre maximal de threads que vous souhaitez dans une région parallèle, jusqu'à 64 dans l'implémentation de Visual C\+\+.  
  
## Notes  
 La variable d'environnement **OMP\_NUM\_THREADS** peut être remplacée par la fonction d' [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou par [num\_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 La valeur par défaut d' `num` dans l'implémentation de Visual C\+\+ du standard d'OpenMP est le nombre de processeurs virtuels, notamment hyperthreading les UC.  
  
 Pour plus d'informations, consultez [4.2 OMP\_NUM\_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## Exemple  
 La commande suivante définit la variable d'environnement **OMP\_NUM\_THREADS** à 16 :  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 La commande suivante affiche le paramètre actuel de la variable d'environnement **OMP\_NUM\_THREADS** :  
  
```  
set OMP_NUM_THREADS  
```  
  
## Voir aussi  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)