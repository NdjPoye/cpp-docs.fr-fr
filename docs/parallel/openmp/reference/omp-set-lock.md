---
title: "omp_set_lock | Microsoft Docs"
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
  - "omp_set_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_lock OpenMP function"
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Les blocs thread l'exécution jusqu'à ce qu'un verrou soit disponible.  
  
## Syntaxe  
  
```  
void omp_set_lock(  
   omp_lock_t *lock  
);  
```  
  
## Notes  
 où,  
  
 `lock`  
 une variable du type [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) qui a été initialisé avec [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## Notes  
 Pour plus d'informations, consultez [3.2.3 omp\_set\_lock and omp\_set\_nest\_lock Functions](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).  
  
## Exemples  
 Consultez l' [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) pour un exemple d'utilisation `omp_set_lock`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)