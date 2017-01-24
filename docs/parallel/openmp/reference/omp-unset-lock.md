---
title: "omp_unset_lock | Microsoft Docs"
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
  - "omp_unset_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_lock OpenMP function"
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_unset_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

libère un verrou.  
  
## Syntaxe  
  
```  
void omp_unset_lock(  
   omp_lock_t *lock  
);  
```  
  
## Notes  
 où,  
  
 `lock`  
 une variable du type [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) qui a été initialisé avec [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md), possédé le thread et en exécutant dans la fonction.  
  
## Notes  
 Pour plus d'informations, consultez [3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## Exemple  
 Consultez l' [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) pour un exemple d'utilisation `omp_unset_lock`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)