---
title: "omp_destroy_nest_lock | Microsoft Docs"
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
  - "omp_destroy_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_destroy_nest_lock OpenMP function"
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_destroy_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Uninitializes un verrou empilable.  
  
## Syntaxe  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## Notes  
 où,  
  
 `lock`  
 une variable du type [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) qui a été initialisé avec [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## Notes  
 Pour plus d'informations, consultez [3.2.2 omp\_destroy\_lock and omp\_destroy\_nest\_lock Functions](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).  
  
## Exemple  
 Consultez l' [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) pour un exemple d'utilisation `omp_destroy_nest_lock`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)