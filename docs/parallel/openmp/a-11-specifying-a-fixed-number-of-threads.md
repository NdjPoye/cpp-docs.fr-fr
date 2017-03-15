---
title: "A.11   Specifying a Fixed Number of Threads | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.11   Specifying a Fixed Number of Threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Certains programmes reposent sur un nombre fixe et préspécifié de thread s'exécute correctement.  Étant donné que le paramètre par défaut pour l'ajustement dynamique du nombre de threads implémentation\-est défini, ces programmes peuvent choisir de désactiver la fonction de thread dynamique et définir le nombre de threads explicitement pour garantir la portabilité.  L'exemple suivant montre comment procéder à l'aide `omp_set_dynamic` \([section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39\), et `omp_set_num_threads` \([section 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) à la page 36\) :  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 Dans cet exemple, le programme exécute correctement uniquement s'il est exécuté par 16 threads.  Si l'implémentation n'est pas capable de prendre en charge 16 threads, le comportement de cet exemple implémentation\-est défini.  
  
 Notez que le nombre de threads exécutant une région parallèle ne change pas pendant une région parallèle, indépendamment de dynamique entraîne le paramètre.  Le mécanisme de thread dynamique détermine le nombre de threads à utiliser au début de la zone parallèle et le maintient constante pour la durée de la zone.