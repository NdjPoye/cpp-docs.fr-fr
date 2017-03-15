---
title: "Proc&#233;dure pas &#224; pas&#160;: utilisation du runtime d&#39;acc&#232;s concurrentiel routage dans une application COM | Microsoft Docs"
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
  - "runtime d’accès concurrentiel, utiliser avec COM"
  - "COM, utiliser avec le runtime d’accès concurrentiel"
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Proc&#233;dure pas &#224; pas&#160;: utilisation du runtime d&#39;acc&#232;s concurrentiel routage dans une application COM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document montre comment utiliser le runtime d'accès concurrentiel dans une application qui utilise le Modèle COM.  
  
## Composants requis  
 Lisez les documents suivants avant de démarrer cette procédure pas\-à\-pas :  
  
-   [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)  
  
-   [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 Pour plus d'informations sur le modèle COM, consultez [COM \(Component Object Model\)](http://msdn.microsoft.com/library/windows/desktop/ms680573).  
  
## Gestion de la durée de vie de la bibliothèque COM  
 Bien que l'utilisation de COM avec le runtime d'accès concurrentiel suive les mêmes principes que tout autre mécanisme d'accès concurrentiel, les indications suivantes peuvent vous aider à utiliser ces bibliothèques ensemble efficacement.  
  
-   Un thread doit appeler [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) avant d'utiliser la bibliothèque COM.  
  
-   Un thread peut appeler `CoInitializeEx` plusieurs fois, tant qu'il fournit les mêmes arguments à chaque appel.  
  
-   Pour chaque appel à `CoInitializeEx`, un thread doit également appeler [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715).  En d'autres termes, les appels à `CoInitializeEx` et `CoUninitialize` doivent être équilibrés.  
  
-   Pour basculer d'un thread cloisonné sur un autre, un thread doit complètement libérer la bibliothèque COM avant d'appeler `CoInitializeEx` avec la nouvelle spécification de threading.  
  
 D'autres principes COM s'appliquent lorsque vous utilisez COM avec le runtime d'accès concurrentiel.  Par exemple, une application qui crée un objet dans un thread cloisonné \(STA, single\-threaded apartment\) et marshale cet objet à un autre apartment doit également fournir une boucle de messages pour traiter les messages entrants.  Vous devez également garder à l'esprit que le marshaling d'objets entre les apartments risque de diminuer les performances.  
  
### Utilisation de COM avec la bibliothèque de modèles parallèles  
 Lorsque vous utilisez COM avec un composant de la bibliothèque de modèles parallèles \(PPL\), tel qu'un groupe de tâches ou un algorithme parallèle, appelez `CoInitializeEx` avant d'utiliser la bibliothèque COM pendant chaque tâche ou itération, et appelez `CoUninitialize` avant la fin de chaque tâche ou itération.  L'exemple suivant indique comment gérer la durée de vie de la bibliothèque COM avec un objet [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md).  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 Vous devez vous assurer que la bibliothèque COM est libérée correctement lorsqu'une tâche ou un algorithme parallèle est annulé, ou lorsque le corps de la tâche lève une exception.  Pour garantir que la tâche appelle `CoUninitialize` avant de s'arrêter, utilisez un bloc `try-finally` ou un modèle *RAII \(Resource Acquisition Is Initialization\)*.  L'exemple suivant utilise un bloc `try-finally` pour libérer la bibliothèque COM lorsque la tâche se termine ou est annulée, ou lorsqu'une exception est levée.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 L'exemple suivant utilise les modèles RAII pour définir la classe `CCoInitializer`, qui gère la durée de vie de la bibliothèque COM dans une portée donnée.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 Vous pouvez utiliser la classe `CCoInitializer` pour libérer automatiquement la bibliothèque COM lorsque la tâche s'arrête, de la façon suivante.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 Pour plus d'informations sur l'annulation du runtime d'accès concurrentiel, consultez [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
### Utilisation de COM avec les agents asynchrones  
 Lorsque vous utilisez COM avec les agents asynchrones, appelez `CoInitializeEx` avant d'utiliser la bibliothèque COM dans la méthode [concurrency::agent::run](../Topic/agent::run%20Method.md) pour votre agent.  Appelez ensuite `CoUninitialize` avant le retour de la méthode `run`.  N'utilisez pas de routines de gestion COM dans le constructeur ou le destructeur de votre agent, et ne substituez pas les méthodes [concurrency::agent::start](../Topic/agent::start%20Method.md) ou [concurrency::agent::done](../Topic/agent::done%20Method.md), car ces méthodes sont appelées par un thread différent de la méthode `run`.  
  
 L'exemple suivant montre une classe d'agent de base appelée `CCoAgent`, qui gère la bibliothèque COM dans la méthode `run`.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 Un exemple complet est fourni à une étape ultérieure de cette procédure.  
  
### Utilisation de COM avec les tâches légères  
 Le document [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md) décrit le rôle des tâches légères dans le runtime d'accès concurrentiel.  Vous pouvez utiliser COM avec une tâche légère, de la même manière qu'avec toute routine de thread que vous passez à la fonction `CreateThread` dans l'API Windows.  L'exemple suivant le démontre.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## Exemple d'application COM  
 Cette section montre une application COM complète qui utilise l'interface `IScriptControl` pour exécuter un script qui calcule le n<sup>ème</sup> nombre de Fibonacci.  Cet exemple appelle en premier le script du thread principal, puis utilise la bibliothèque de modèles parallèles et les agents pour appeler le script simultanément.  
  
 Considérez la fonction d'assistance suivante, `RunScriptProcedure` qui appelle une procédure dans un objet `IScriptControl`.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 La fonction `wmain` crée un objet `IScriptControl`, lui ajoute du code de script qui calcule le n<sup>ème</sup> nombre de Fibonacci, puis appelle la fonction `RunScriptProcedure` pour exécuter ce script.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### Appel du script depuis la bibliothèque de modèles parallèles  
 La fonction suivante, `ParallelFibonacci`, utilise l'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) pour appeler le script en parallèle.  Cette fonction utilise la classe `CCoInitializer` pour gérer la durée de vie de la bibliothèque COM pendant chaque itération de la tâche.  
  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 Pour utiliser la fonction `ParallelFibonacci` avec cet exemple, ajoutez le code suivant avant le retour de la fonction `wmain`.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### Appel du script par un agent  
 L'exemple suivant montre la classe `FibonacciScriptAgent`, qui appelle une procédure de script pour calculer le n<sup>ème</sup> nombre de Fibonacci.  La classe `FibonacciScriptAgent` utilise le passage de message pour recevoir du programme principal des valeurs d'entrée de la fonction de script.  La méthode `run` gère la durée de vie de la bibliothèque COM tout au long de la tâche.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 La fonction suivante, `AgentFibonacci`, crée plusieurs objets `FibonacciScriptAgent` et utilise le passage de message pour envoyer plusieurs valeurs d'entrée à ces objets.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 Pour utiliser la fonction `AgentFibonacci` avec cet exemple, ajoutez le code suivant avant le retour de la fonction `wmain`.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### Exemple complet  
 Le code suivant montre l'exemple complet, qui utilise des algorithmes parallèles et des agents asynchrones pour appeler une procédure de script qui calcule des nombres de Fibonacci.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant :  
  
  **Thread Principal**  
**fib\(15\) \= 610**  
**Fibonacci parallèle :**  
**fib\(15\) \= 610**  
**fib\(10\) \= 55**  
**fib\(16\) \= 987**  
**fib\(18\) \= 2584**  
**fib\(11\) \= 89**  
**fib\(17\) \= 1597**  
**fib\(19\) \= 4181**  
**fib\(12\) \= 144**  
**fib\(13\) \= 233**  
**fib\(14\) \= 377**  
**Agent Fibonacci :**  
**fib\(30\) \= 832040**  
**fib\(22\) \= 17711**  
**fib\(10\) \= 55**  
**fib\(12\) \= 144**   
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `parallel-scripts.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc parallel\-scripts.cpp \/link ole32.lib**  
  
## Voir aussi  
 [Procédures pas à pas relatives au runtime d'accès concurrentiel](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)   
 [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)