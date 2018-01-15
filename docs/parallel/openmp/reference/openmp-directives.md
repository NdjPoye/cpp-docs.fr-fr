---
title: Directives OpenMP | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51d501139d0610d670f7d646dc985a694a5b741c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="openmp-directives"></a>Directives OpenMP
Fournit des liens vers les directives utilisées dans l’API OpenMP.  
  
 Visual C++ prend en charge les directives OpenMP suivantes :  
  
|Directive|Description|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|Spécifie qu’un emplacement de mémoire qui sera mise à jour atomiquement.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Synchronise tous les threads dans une équipe. tous les threads suspendre au cloisonnement, jusqu'à ce que tous les threads s’exécutent le cloisonnement.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Spécifie que les code est exécuté uniquement sur un seul thread à la fois.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Spécifie que tous les threads ont la même vue de la mémoire pour tous les objets partagés.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|Provoque le travail effectué dans une boucle à l’intérieur d’une région parallèle pour être réparti entre les threads.|  
|[master](../../../parallel/openmp/reference/master.md)|Spécifie qu’uniquement le maître threadshould exécuter une section du programme.|  
|[commandée](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Spécifie que le code sous un parallélisée boucle doit être exécutée comme une boucle séquentielle.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Définit une région parallèle, ce qui est le code qui sera exécuté par plusieurs threads en parallèle.|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|Identifie les sections de code pour être réparti entre tous les threads.|  
|[single](../../../parallel/openmp/reference/single.md)|Permet de spécifier qu’une section de code doit être exécutée sur un seul thread, pas nécessairement le thread principal.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Spécifie qu’une variable privée à un thread.|  
  
## <a name="see-also"></a>Voir aussi  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)