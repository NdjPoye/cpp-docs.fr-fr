---
title: "OpenMP Clauses | Microsoft Docs"
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
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Clauses
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

fournit des liens vers des clauses utilisées dans l'API d'OpenMP.  
  
 Visual C\+\+ prend en charge les clauses suivantes OpenMP :  
  
|Clause|Description|  
|------------|-----------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|Permet aux threads d'accéder à la principale valeur du thread, pour une variable de [threadprivate](../../../parallel/openmp/reference/threadprivate.md) .|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Spécifie qu'une ou plusieurs variables doivent être partagées par tous les threads.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|Spécifie le comportement des variables unscoped dans la région parallèle.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Spécifie que chaque thread doit avoir sa propre instance d'une variable, et que la variable doit être initialisée avec la valeur de la variable, car elle existe avant que l'élément parallèle.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|Spécifie si une boucle doit être exécutée en parallèle ou dans l'interface série.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Spécifie que la version englobante du contexte de la variable est égal défini à la version privée de n'importe quel thread exécute l'itération finale \(élément de la boucle\) ou la dernière section \(sections \#pragma\).|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|Substitue le cloisonnement implicites dans une directive.|  
|[num\_threads](../../../parallel/openmp/reference/num-threads.md)|Définit le nombre de threads dans une équipe de thread.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Obligatoire sur une instruction parallèle de [for](../../../parallel/openmp/reference/for-openmp.md) si une directive d' [ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md) doit être utilisée dans la boucle.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|Spécifie que chaque thread doit avoir sa propre instance d'une variable.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|Spécifie qu'un ou plusieurs variables qui sont spécifiques à chaque thread sont la rubrique d'une opération de réduction à la fin de la zone parallèle.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|s'applique à [for](../../../parallel/openmp/reference/for-openmp.md) la directive.|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|Spécifie qu'une ou plusieurs variables doivent être partagées par tous les threads.|  
  
## Voir aussi  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)