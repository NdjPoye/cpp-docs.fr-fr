---
title: "3.2.3 omp_set_lock and omp_set_nest_lock Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.3 omp_set_lock and omp_set_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Chacune de ces fonctions blocs le thread qui exécute la fonction jusqu'à ce que le verrou spécifié soit disponible puis définit le verrou.  un verrou simple est disponible s'il est déverrouillé.  Un verrou empilable est disponible s'il est déverrouillé ou s'il est déjà possédé par le thread qui exécute la fonction.  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Pour un verrou simple, l'argument à la fonction d' `omp_set_lock` doit indiquer une variable initialisée de verrouillage.  La propriété du verrou est accordée au thread qui exécute la fonction.  
  
 Pour un verrou empilable, l'argument à la fonction d' `omp_set_nest_lock` doit indiquer une variable initialisée de verrouillage.  le nombre d'imbrication est incrémenté, et le thread est accordé, ou conserve, propriété du verrou.