---
title: "Comment&#160;: effectuer une s&#233;lection parmi les t&#226;ches termin&#233;es | Microsoft Docs"
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
  - "effectuer une sélection parmi les tâches terminées [Runtime d’accès concurrentiel]"
  - "tâches terminées, sélectionner parmi [Runtime d’accès concurrentiel]"
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: effectuer une s&#233;lection parmi les t&#226;ches termin&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser les classes [concurrency::choice](../../parallel/concrt/reference/choice-class.md) et [concurrency::join](../../parallel/concrt/reference/join-class.md) pour sélectionner la première tâche afin de terminer un algorithme de recherche.  
  
## Exemple  
 L'exemple suivant effectue deux algorithmes de recherche en parallèle et sélectionne le premier algorithme à terminer.  Cet exemple définit le type `employee`, qui contient un identificateur numérique et un salaire pour un employé.  La fonction `find_employee` recherche le premier employé qui a l'identificateur fourni ou le salaire fourni.  La fonction `find_employee` gère également le cas où aucun employé n'a l'identificateur ou salaire fourni.  La fonction `wmain` crée un tableau d'objets `employee` et recherche plusieurs valeurs de salaire et d'identificateur.  
  
 L'exemple utilise un objet `choice` pour effectuer une sélection parmi les cas suivants :  
  
1.  Il existe un employé qui a l'identificateur fourni.  
  
2.  Il existe un employé qui a le salaire fourni.  
  
3.  Il n'existe aucun employé qui a l'identificateur ou le salaire fourni.  
  
 Pour les deux premiers cas, l'exemple utilise un objet [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md) pour stocker l'identificateur et un autre objet `single_assignment` pour stocker le salaire.  L'exemple utilise un objet `join` pour le troisième cas.  L'objet `join` est composé de deux objets `single_assignment` supplémentaires, un pour le cas où il n'existe aucun employé avec l'identificateur fourni et un pour le cas où il n'existe aucun employé avec le salaire fourni.  L'objet `join` envoie un message lorsque chacun de ses membres reçoit un message.  Dans cet exemple, l'objet `join` envoie un message lorsqu'il n'existe aucun employé avec l'identificateur ou le salaire fourni.  
  
 L'exemple utilise un objet [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) pour exécuter les deux algorithmes de recherche en parallèle.  Chaque tâche de recherche écrit dans l'un des objets `single_assignment` pour indiquer si l'employé donné existe.  L'exemple utilise la fonction [concurrency::receive](../Topic/receive%20Function.md) pour obtenir l'index de la première mémoire tampon qui contient un message et un bloc `switch` pour imprimer le résultat.  
  
 [!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/CPP/how-to-select-among-completed-tasks_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **L'employé avec l'ID 14758 de salaire 27780,00.**  
**L'employé avec le salaire 84345 a l'ID 29150.00 .**  
**L'employé avec l'ID 61935 de salaire 29905,00.**  
**Aucun employé n'a l'ID 899 ou le salaire 31223,00.** Cet exemple utilise la fonction d'assistance [concurrency::make\_choice](../Topic/make_choice%20Function.md) pour créer des objets `choice` et la fonction d'assistance [concurrency::make\_join](../Topic/make_join%20Function.md) pour créer des objets `join`.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `find-employee.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc find\-employee.cpp**  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)   
 [Classe choice](../../parallel/concrt/reference/choice-class.md)   
 [join, classe](../../parallel/concrt/reference/join-class.md)