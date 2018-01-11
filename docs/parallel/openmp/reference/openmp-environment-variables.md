---
title: "Variables d’environnement OpenMP | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e285ab34c7bf993b919a2c917f44828c21970f67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="openmp-environment-variables"></a>Variables d'environnement OpenMP
Fournit des liens vers les variables d’environnement utilisées dans l’API OpenMP.  
  
 L’implémentation Visual C++ de l’OpenMP standard inclut les variables d’environnement. Ces variables d’environnement sont en lecture au démarrage du programme et les modifications apportées à leurs valeurs sont ignorées lors de l’exécution (par exemple, à l’aide de [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).  
  
|Variable d’environnement|Description|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Spécifie si la durée d’exécution de OpenMP peut ajuster le nombre de threads dans une région parallèle.|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Spécifie si parallélisme imbriquée est activée, sauf si le parallélisme imbriquée est activée ou désactivée avec `omp_set_nested`.|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Définit le nombre maximal de threads dans la région parallèle, sauf si [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou [num_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Modifie le comportement de la [planification](../../../parallel/openmp/reference/schedule.md) clause lorsque `schedule(runtime)` est spécifié dans un `for` ou `parallel for` la directive.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de la bibliothèque](../../../parallel/openmp/reference/openmp-library-reference.md)