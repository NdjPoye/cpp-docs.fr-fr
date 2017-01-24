---
title: "OpenMP Directives | Microsoft Docs"
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
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Directives
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Fournit des liens vers les directives utilisées dans l'API d'OpenMP.  
  
 Visual C\+\+ prend en charge les directives suivantes OpenMP :  
  
|Directive|Description|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|spécifie qu'un emplacement de mémoire qui sera mis à jour atomique.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Synchronise tous les threads dans une équipe ; tous les threads suspendent dans le cloisonnement, jusqu'à ce que tous les threads exécutent le cloisonnement.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Spécifie que le code est uniquement exécuté sur un thread à la fois.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Spécifie que tous les threads ont le même point de vue de la mémoire pour tous les objets partagés.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|Permet de le travail effectué dans un pour l'intérieur de la boucle une région parallèle à diviser entre les threads.|  
|[master](../../../parallel/openmp/reference/master.md)|Spécifie que seul le principal threadshould exécutent une section du programme.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Spécifie ce code sous parallélisé de la boucle doit être exécuté comme une boucle séquentielle.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Définit une zone parallèle, qui est le code qui sera exécuté par plusieurs threads en parallèle.|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|Reconnaît des sections de code à diviser parmi tous les threads.|  
|[single](../../../parallel/openmp/reference/single.md)|Vous permet de spécifier qu'une section de code doit être exécutée sur un thread unique, pas nécessairement le thread principal.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|spécifie qu'une variable est privée à un thread.|  
  
## Voir aussi  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)