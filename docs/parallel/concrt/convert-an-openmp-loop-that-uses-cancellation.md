---
title: "Comment&#160;: convertir une boucle OpenMP qui a recours &#224; l’annulation pour utiliser le runtime d’acc&#232;s concurrentiel | Microsoft Docs"
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
helpviewer_keywords: 
  - "convertir d’OpenMP en runtime d’accès concurrentiel, annulation"
  - "annulation, convertir d’OpenMP en runtime d’accès concurrentiel"
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir une boucle OpenMP qui a recours &#224; l’annulation pour utiliser le runtime d’acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Certaines boucles parallèles ne requièrent pas l'exécution de toutes les itérations.  Par exemple, un algorithme qui recherche une valeur peut se terminer lorsque la valeur est trouvée.  OpenMP ne fournit pas de mécanisme pour quitter une boucle parallèle.  Toutefois, vous pouvez utiliser une valeur booléenne, ou indicateur, pour permettre à une itération de la boucle d'indiquer que la solution a été trouvée.  Le runtime d'accès concurrentiel fournit des fonctionnalités qui activent une tâche pour annuler d'autres tâches qui n'ont pas encore démarré.  
  
 Cet exemple montre comment convertir une boucle [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) OpenMP qui ne requiert pas l'exécution de toutes les itérations pour que le mécanisme d'annulation du runtime d'accès concurrentiel puisse être utilisé.  
  
## Exemple  
 Cet exemple utilise OpenMP et le runtime d'accès concurrentiel pour implémenter une version parallèle de l'algorithme [std::any\_of](../Topic/any_of.md).  La version OpenMP de cet exemple utilise un indicateur pour coordonner toutes les itérations de boucle parallèle remplies par la condition.  La version qui utilise le runtime d'accès concurrentiel utilise la méthode [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) pour arrêter l'opération globale lorsque la condition est remplie.  
  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Utilisation de OpenMP…**  
**9114046 dans le tableau.**  
**utilisation du runtime d'accès concurrentiel...**  
**9114046 dans le tableau.** Dans la version qui utilise OpenMP, toutes les itérations de la boucle s'exécutent, même quand l'indicateur est défini.  En outre, si une tâche comporte des tâches enfants, l'indicateur doit également être disponible pour ces tâches enfants afin de communiquer l'annulation.  Dans le runtime d'accès concurrentiel, quand un groupe de tâches est annulé, le runtime annule l'ensemble de l'arborescence de travail, y compris les tâches enfants.  L'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) utilise des tâches pour exécuter un travail.  Par conséquent, si une itération de la boucle annule la tâche racine, l'ensemble de l'arborescence du calcul est également annulé.  Lorsqu'une arborescence de travail est annulée, le runtime ne démarre pas de nouvelle tâche.  Toutefois, le runtime permet aux tâches qui ont déjà démarré de se terminer.  Par conséquent, dans le cas de l'algorithme `parallel_for_each`, les itérations de boucles actives peuvent nettoyer leurs ressources.  
  
 Dans les deux versions de cet exemple, si le tableau contient plusieurs copies de la valeur à rechercher, plusieurs itérations de boucle peuvent définir simultanément le résultat et annuler l'opération globale.  Vous pouvez utiliser une primitive de synchronisation, tel qu'une section critique, si votre problème nécessite qu'une seule tâche effectue un travail lorsqu'une condition est remplie.  
  
 Vous pouvez également utiliser la gestion des exceptions pour annuler des tâches qui utilisent la bibliothèque PPL.  Pour plus d'informations sur l'annulation, consultez [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
 Pour plus d'informations sur `parallel_for_each` et d'autres algorithmes parallèles, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet `Visual Studio`, ou collez\-le dans un fichier nommé concrt\-omp\-parallel\-any\-of.cpp, puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-parallel\-any\-of.cpp**  
  
## Voir aussi  
 [Migration d'OpenMP au runtime d'accès concurrentiel](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)