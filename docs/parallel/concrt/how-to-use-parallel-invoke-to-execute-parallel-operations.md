---
title: "Comment&#160;: utiliser parallel_invoke pour ex&#233;cuter des op&#233;rations parall&#232;les | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parallel_invoke, exemple de fonction"
  - "appeler plusieurs fonctions en parallèle (runtime d'accès concurrentiel)"
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Comment&#160;: utiliser parallel_invoke pour ex&#233;cuter des op&#233;rations parall&#232;les
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple indique comment utiliser l'algorithme [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) pour améliorer les performances d'un programme qui exécute des opérations sur une source de données partagée.  Étant donné qu'aucune des opérations ne modifie la source, elles peuvent être exécutées en parallèle de façon simple.  
  
## Exemple  
 Prenons l'exemple de code suivant qui crée une variable de type `MyDataType`, appelle une fonction pour initialiser cette variable, puis exécute plusieurs opérations longues sur ces données.  
  
 [!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]  
  
 Si les fonctions `lengthy_operation1`, `lengthy_operation2` et `lengthy_operation3` ne modifient pas la variable `MyDataType`, ces fonctions peuvent être exécutées en parallèle sans modification supplémentaire.  
  
## Exemple  
 L'exemple suivant modifie l'exemple précédent pour s'exécuter en parallèle.  L'algorithme `parallel_invoke` exécute chaque tâche en parallèle, puis retourne les valeurs lorsque toutes les tâches sont terminées.  
  
 [!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]  
  
## Exemple  
 L'exemple suivant télécharge l'*Iliade*, d'Homère, depuis gutenberg.org et exécute plusieurs opérations sur ce fichier.  L'exemple exécute d'abord ces opérations de façon séquentielle, puis exécute les mêmes opérations en parallèle.  
  
 [!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant.  
  
  **Téléchargement de 'L'Iliad**  
**La version sérialisée en cours de exécution… a nécessité 953 ms.**  
**La version parallèle en cours de exécution… a nécessité 656 ms.**  
**Les mots les plus courants avec cinq lettres ou plus sont :**  
 **leur \(953\)**  
 **shall \(444\)**  
 **which \(431\)**  
 **volumineux \(398\)**  
 **Hector \(349\)**  
 **Achille \(309\)**  
 **à travers \(301\)**  
 **Ces \(268\)**  
 **chef \(259\)**  
**La plus longue séquence de caractères qui ont la même première lettre est :**  
 **dans la tempête au couvert**  
**Les palindromes suivants apparaissent dans le texte suivant :**  
 **arrêt de taches**  
 **profondeurs de vitesse**  
 **les quilles lissent** Cet exemple utilise l'algorithme `parallel_invoke` pour appeler les plusieurs fonctions qui agissent sur la même source de données.  Vous pouvez utiliser l'algorithme `parallel_invoke` pour appeler un ensemble de fonctions en parallèle, sans vous limiter à celles qui agissent sur les mêmes données.  
  
 Étant donné que l'algorithme `parallel_invoke` appelle chaque fonction de travail en parallèle, ses performances sont limitées par la fonction dont l'exécution prend le plus de temps \(si le runtime traite chaque fonction sur un processeur séparé\).  Si cet exemple exécute plus de tâches en parallèle que le nombre de processeurs disponibles, plusieurs tâches peuvent s'exécuter sur chaque processeur.  Dans ce cas, les performances sont limitées par le groupe de tâches dont l'exécution prend le plus de temps.  
  
 Étant donné que cet exemple exécute trois tâches en parallèle, vous ne devez pas vous attendre à ce que les performances évoluent sur les ordinateurs qui ont plus de trois processeurs.  Pour améliorer encore plus les performances, vous pouvez diviser les tâches les plus longues en tâches plus petites et exécuter ces tâches en parallèle.  
  
 Vous pouvez utiliser l'algorithme `parallel_invoke` plutôt que les classes [concurrency::task\_group](../Topic/task_group%20Class.md) et [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) si vous n'avez pas besoin de la prise en charge de l'annulation.  Pour obtenir un exemple qui compare l'utilisation de l'algorithme `parallel_invoke` et celle des groupes de tâches, consultez [Comment : utiliser parallel\_invoke pour écrire une routine de tri parallèle](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).  
  
## Compilation du code  
 Pour compiler le code, copiez\-le, puis collez\-le dans un projet Visual Studio , ou dans un fichier nommé `parallel-word-mining.cpp`, puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc \/MD \/DUNICODE \/D\_AFXDLL parallel\-word\-mining.cpp**  
  
## Voir aussi  
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_invoke, fonction](../Topic/parallel_invoke%20Function.md)