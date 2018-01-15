---
title: 3.2.5 fonctions fonctions omp_test_lock and omp_test_nest_lock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8fcdacdbb38a9bb27e35ada74aa2139be10c6797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 Fonctions omp_test_lock and omp_test_nest_lock
Ces fonctions, essayez de définir un verrou mais ne bloquent pas l’exécution du thread. Le format est le suivant :  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 L’argument doit pointer vers une variable initialisée de verrou. Ces fonctions essayez de définir un verrou de la même manière que `omp_set_lock` et `omp_set_nest_lock`, mais ils ne bloquent pas l’exécution du thread.  
  
 Pour obtenir un verrou simple, le `omp_test_lock` fonction retourne une valeur différente de zéro si le verrou est correctement défini ; sinon, elle retourne zéro.  
  
 Pour obtenir un verrou pouvant, le `omp_test_nest_lock` fonction retourne le nouveau nombre d’imbrication si le verrou est correctement défini ; sinon, elle retourne zéro.