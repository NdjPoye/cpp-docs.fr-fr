---
title: "3.1.4 omp_get_thread_num Function | Microsoft Docs"
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.4 omp_get_thread_num Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' `omp_get_thread_num` retourne le nombre de threads, dans son équipe, du thread en la fonction.  Le nombre de threads se trouve entre 0 et **omp\_get\_num\_threads \(\)**\- 1, inclus.  Le thread principal de l'équipe est le thread 0.  
  
 Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 En cas de appel d'une zone série, retourne 0 d' `omp_get_thread_num` .  En cas de appel d'une région parallèle imbriquée qui est sérialisée, retourne 0 de cette fonction.  
  
## Références croisées :  
  
-   la fonction d'`omp_get_num_threads` , consultez [section 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) à la page 37.