---
title: "OpenMP Data Types | Microsoft Docs"
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
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Data Types
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

fournit des liens vers des types de données utilisés dans l'API d'OpenMP.  
  
 L'implémentation de Visual C\+\+ du standard d'OpenMP inclut les types de données suivants.  
  
|Type de données|Description|  
|---------------------|-----------------|  
|[omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md)|Un type qui contient l'état d'un verrou, si le verrou est disponible ou si un thread possède un verrou.|  
|[omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)|Un type qui contient une des informations suivantes concernant un verrou : si le verrou est disponible, et l'identité du thread qui détient le verrou et un nombre d'imbrication.|  
  
## Voir aussi  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)