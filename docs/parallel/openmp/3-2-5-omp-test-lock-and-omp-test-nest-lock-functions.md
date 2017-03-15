---
title: "3.2.5 omp_test_lock and omp_test_nest_lock Functions | Microsoft Docs"
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
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.5 omp_test_lock and omp_test_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La tentative de ces fonctions de définir un verrou mais ne bloquent pas l'exécution du thread.  Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 L'argument doit indiquer une variable initialisée de verrouillage.  La tentative de ces fonctions de définir un verrou de la même manière qu' `omp_set_lock` et `omp_set_nest_lock`, mais elles ne bloquent pas l'exécution du thread.  
  
 Pour un verrou simple, la fonction d' `omp_test_lock` retourne une valeur différente de zéro si le verrou est correctement défini ; sinon, il retourne zéro.  
  
 Pour un verrou empilable, la fonction d' `omp_test_nest_lock` retourne le nouveau nombre d'imbrication si le verrou est correctement défini ; sinon, il retourne zéro.