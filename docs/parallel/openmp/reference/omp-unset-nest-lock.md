---
title: "omp_unset_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_unset_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_nest_lock OpenMP function"
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# omp_unset_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

libère un verrou empilable.  
  
## Syntaxe  
  
```  
void omp_unset_nest_lock(   
   omp_nest_lock_t *lock   
);  
```  
  
## Notes  
 où,  
  
 `lock`  
 une variable du type [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) qui a été initialisé avec [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md), possédé le thread et en exécutant dans la fonction.  
  
## Notes  
 Pour plus d'informations, consultez [3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## Exemple  
 Consultez l' [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) pour un exemple d'utilisation `omp_unset_nest_lock`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)