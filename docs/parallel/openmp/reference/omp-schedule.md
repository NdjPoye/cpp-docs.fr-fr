---
title: "OMP_SCHEDULE | Microsoft Docs"
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
  - "OMP_SCHEDULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_SCHEDULE OpenMP environment variable"
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Modifie le comportement de la clause de [schedule](../../../parallel/openmp/reference/schedule.md) lorsque `schedule(runtime)` est spécifié dans une directive d' `for` ou d' `parallel for` .  
  
## Syntaxe  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## Notes  
 où,  
  
 `size` \(facultatif\)  
 spécifie la taille des itérations.  `size` doit être un entier positif.  La valeur par défaut est 1, sauf lorsque `type` est statique.  Non valide lorsque `type` est `runtime`.  
  
 `type`  
 Le type de planifier :  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## Notes  
 la valeur par défaut dans l'implémentation de Visual C\+\+ du standard d'OpenMP est `OMP_SCHEDULE=static,0`.  
  
 Pour plus d'informations, consultez [4.1 OMP\_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## Exemple  
 La commande suivante définit la variable d'environnement **OMP\_SCHEDULE** :  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 La commande suivante affiche le paramètre actuel de la variable d'environnement **OMP\_SCHEDULE** :  
  
```  
set OMP_SCHEDULE  
```  
  
## Voir aussi  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)