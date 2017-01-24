---
title: "barrier | Microsoft Docs"
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
  - "barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barrier OpenMP directive"
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# barrier
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Synchronise tous les threads dans une équipe ; tous les threads suspendent dans le cloisonnement, jusqu'à ce que tous les threads exécutent le cloisonnement.  
  
## Syntaxe  
  
```  
#pragma omp barrier  
```  
  
## Notes  
 La directive d' `barrier` ne prend en charge aucune clauses OpenMP.  
  
 Pour plus d'informations, consultez [2.6.3 barrier Directive](../../../parallel/openmp/2-6-3-barrier-directive.md).  
  
## Exemple  
 Pour un exemple d'utilisation `barrier`, consultez [master](../../../parallel/openmp/reference/master.md).  
  
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)