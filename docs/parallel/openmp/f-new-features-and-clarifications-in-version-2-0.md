---
title: "F. New Features and Clarifications in Version 2.0 | Microsoft Docs"
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
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# F. New Features and Clarifications in Version 2.0
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette annexe résume les principaux modifications apportées à la spécification d'OpenMP C\/C\+\+ à déplacer de la version 1,0 vers la version 2,0.  Les éléments suivants sont des nouvelles fonctionnalités ajoutées à la spécification :  
  
-   Des virgules sont autorisées dans les directives et OpenMP \([section 2,1](../../parallel/openmp/2-1-directive-format.md) à la page 7\).  
  
-   ajout de la clause d' `num_threads` .  Cette clause permet à un utilisateur de demander un nombre spécifique de thread pour un élément parallèle \([section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8\).  
  
-   La directive d' `threadprivate` a été étendue pour accepter les variables statiques de portée de bloc \([section 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) à la page 23\).  
  
-   Les tableaux de longueur variable de C99 sont les types complets, et peuvent être donc n'importe où les types complets spécifiés sont autorisées par exemple, dans les listes d' `private`, d' `firstprivate`, et les clauses d' `lastprivate` \([section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25\).  
  
-   Une variable privée dans une région parallèle peut être privée marqué de nouveau dans une directive imbriquée \([section 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) à la page 25\).  
  
-   la clause d' `copyprivate` a été ajoutée.  Il fournit un mécanisme pour utiliser une variable privée pour diffuser une valeur d'un membre d'une équipe aux autres membres.  Il s'agit d'une alternative à utiliser une variable partagée pour la valeur lorsque la fourniture d'une variable si partagée serait difficile \(par exemple, dans une récursivité requérant une variable différente à chaque niveau\).  La clause d' `copyprivate` peuvent seulement apparaître sur la directive d' **unique** \([section 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) à la page 32\).  
  
-   Ajout des routines `omp_get_wtick` et `omp_get_wtime` de minutage semblables aux routines MPI.  Ces fonctions sont nécessaires pour exécuter les horloges d'horloge murale\) \([section 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) à la page 44 et [section 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) à la page 45\).  
  
-   une annexe avec une liste de comportements implémentation\-définis dans OpenMP C\/C\+\+ a été ajoutée.  Une implémentation est requise pour définir et documenter son comportement dans ces cas \([annexe E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) à la page 97\).  
  
-   Les modifications suivantes servent à clarifier ou corriger les fonctionnalités dans la spécification précédente d'API d'OpenMP pour C\/C\+\+ :  
  
    -   Clarification concernant le comportement d' `omp_set_nested` et d' `omp_set_dynamic` lorsque retourne une valeur différente de zéro d' `omp_in_parallel` n'est pas défini \([section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39, et [section 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) à la page 40\).  
  
    -   Imbrication directive clarification lorsque le traitement parallèle imbriqué est utilisé \([section 2,9](../../parallel/openmp/2-9-directive-nesting.md) à la page 33\).  
  
    -   L'initialisation de verrouillage et les fonctions de destruction de verrou peut être appelées dans une région parallèle \([section 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) à la page 42 et [section 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) à la page 42\).  
  
    -   de nouveaux exemples ont été ajoutés \([annexe A](../../parallel/openmp/a-examples.md) à la page 51\).