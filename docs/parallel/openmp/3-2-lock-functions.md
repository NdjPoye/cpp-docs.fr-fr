---
title: "3.2 Lock Functions | Microsoft Docs"
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
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2 Lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les fonctions décrites de cette section manipulent des verrous utilisés pour la synchronisation.  
  
 pour les fonctions suivantes, la variable de verrou doit avoir le type **omp\_lock\_t**.  Cette variable doit uniquement accessible via ces fonctions.  Toutes les fonctions de verrou requièrent un argument qui a un pointeur vers le type d' **omp\_lock\_t** .  
  
-   la fonction d' `omp_init_lock` initialise un verrou simple.  
  
-   la fonction d' `omp_destroy_lock` supprime un verrou simple.  
  
-   la fonction d' `omp_set_lock` attend jusqu'à ce qu'un verrou simple soit disponible.  
  
-   la fonction d' `omp_unset_lock` libère un verrou simple.  
  
-   les tests de fonction d' `omp_test_lock` un verrou simple.  
  
 pour les fonctions suivantes, la variable de verrou doit avoir le type **omp\_nest\_lock\_t**.  Cette variable doit uniquement accessible via ces fonctions.  Toutes les fonctions de verrou empilables requièrent un argument qui a un pointeur vers le type d' **omp\_nest\_lock\_t** .  
  
-   la fonction d' `omp_init_nest_lock` initialise un verrou empilable.  
  
-   la fonction d' `omp_destroy_nest_lock` supprime un verrou empilable.  
  
-   la fonction d' `omp_set_nest_lock` attend jusqu'à ce qu'un verrou empilable soit disponible.  
  
-   la fonction d' `omp_unset_nest_lock` libère un verrou empilable.  
  
-   les tests de fonction d' `omp_test_nest_lock` un verrou empilable.  
  
 Les fonctions de verrou d'OpenMP accède à la variable de verrou de telle sorte qu'elles toujours lisent et mettent à jour la plupart de valeur actuelle de la variable de verrouillage.  Par conséquent, il n'est pas nécessaire qu'un programme d'OpenMP inclure les directives explicites de **vide** pour garantir que la valeur de variable de verrou est cohérente entre les différents threads.  \(Il peut exister un besoin des directives de **vide** de mettre les valeurs d'autres variables cohérentes.\)