---
title: "Gestion des exceptions dans le runtime d’acc&#232;s concurrentiel | Microsoft Docs"
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
  - "tâches légères, gestion des exceptions [runtime d’accès concurrentiel]"
  - "gestion des exceptions [runtime d’accès concurrentiel]"
  - "groupes de tâches structurés, gestion des exceptions [runtime d’accès concurrentiel]"
  - "agents, gestion des exceptions [runtime d’accès concurrentiel]"
  - "groupes de tâches, gestion des exceptions [runtime d’accès concurrentiel]"
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
caps.latest.revision: 29
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des exceptions dans le runtime d’acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le runtime d'accès concurrentiel utilise la gestion des exceptions C\+\+ pour communiquer de nombreux genres d'erreurs.  Ces erreurs incluent l'utilisation non valide du runtime, des erreurs d'exécution telles que l'échec d'acquisition d'une ressource et les erreurs qui se produisent dans les fonctions de travail que vous fournissez aux tâches et aux groupes de tâches.  Lorsqu'une tâche ou un groupe de tâches lève une exception, le runtime conserve cette exception et la marshale au contexte qui attend que la tâche ou le groupe de tâches se termine.  Pour des composants tels que les tâches légères et les agents, le runtime ne gère pas les exceptions pour vous.  Dans ces cas\-là, vous devez implémenter votre propre mécanisme de gestion des exceptions.  Cette rubrique décrit comment le runtime gère les exceptions levées par tâches, des groupes de tâches, des tâches légères et des agents asynchrones, et comment répondre aux exceptions dans vos applications.  
  
## Points clés  
  
-   Lorsqu'une tâche ou un groupe de tâches lève une exception, le runtime conserve cette exception et la marshale au contexte qui attend que la tâche ou le groupe de tâches se termine.  
  
-   Lorsque c'est possible, entourer chaque appel à [concurrency::task::get](../Topic/task::get%20Method.md) et [concurrency::task::wait](../Topic/task::wait%20Method.md) dans un bloc `try`\/`catch` pour manipuler les erreurs que vous pouvez récupérer.  Le runtime termine l'application si une tâche lève une exception et que cette exception n'est pas interceptée par la tâche, une de ses procédures suivantes ou l'application principale.  
  
-   Un prolongement d'une tâche compile toujours; que l'antécédent soit terminé correctement, qu'une exception soit levée, ou ait été annulée n'importe pas.  Un prolongement basé sur la valeur ne fonctionne pas si la tâche antécédente lève ou annule.  
  
-   Étant donné que le prolongement des tâches fonctionne toujours, envisagez s'il faut ajouter un prolongement des tâches par à la fin de la chaîne de prolongement.  Cela peut permettre de vous assurer que votre code considère toutes les exceptions.  
  
-   Le runtime lève [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) lorsque vous appelez [concurrency::task::get](../Topic/task::get%20Method.md) et cette tâche est annulée.  
  
-   Le runtime ne gère pas d'exceptions pour des tâches légères et des agents.  
  
##  <a name="top"></a> Dans ce document  
  
-   [Tâches et continuations](#tasks)  
  
-   [Groupes de tâches et algorithmes parallèles](#task_groups)  
  
-   [Exceptions levées par le runtime](#runtime)  
  
-   [Exceptions multiples](#multiple)  
  
-   [Annulation](#cancellation)  
  
-   [Tâches légères](#lwts)  
  
-   [Agents asynchrones](#agents)  
  
##  <a name="tasks"></a> Tâches et continuations  
 Cette section décrit comment le runtime gère les exceptions qui sont levées par les objets [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) et leur prolongement.  Pour plus d'informations sur la tâche et le modèle de prolongement, consultez [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Lorsque vous levez une exception dans le corps d'une fonction de travail que vous passez à un object `task`, le runtime le stocke et la marshale au contexte qui appelle [concurrency::task::get](../Topic/task::get%20Method.md) ou [concurrency::task::wait](../Topic/task::wait%20Method.md).  Le document [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md) décrit les prolongements basés sur la valeur versus ceux basés sur la tâche , mais pour résumer, un prolongement basé sur la valeur prend un paramètre de type `T` et prolongements basés sur la tâche prend un paramètre de type `task<T>`.  Si une tâche qui lève une exception a un ou plusieurs prolongements basés sur la valeur, ces prolongements ne sont pas planifiées pour s'exécuter.  L'exemple suivant illustre ce comportement :  
  
 [!code-cpp[concrt-eh-task#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_1.cpp)]  
  
 Un prolongement de tâches qui permet de gérer n'importe quelle exception qui est levée par la tâche antécédente.  Un prolongement d'une tâche compile toujours; que la tâche antécédente soit terminée correctement, qu'une exception soit levée, ou ait été annulée n'importe pas.  Lorsqu'une tâche lève une exception, ses prolongements basés sur la tâche sont planifiés pour s'exécuter.  L'exemple suivant montre une tâche qui lève toujours une exception.  La tâche a deux prolongement; un est basé sur la valeur et l'autre est basé sur la tâche.  Les exceptions basées sur les tâches sont toujours exécutées, et par conséquent peuvent intercepter l'exception levée par la tâche d'antécédent.  Lorsque l'exemple attend les deux prolongements pour terminer, l'exception est générée de nouveau car l'exception de la tâche est toujours levée lorsque `task::get` ou `task::wait` est appelé.  
  
 [!code-cpp[concrt-eh-continuations#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_2.cpp)]  
  
 Nous vous recommandons les procédures suivantes des tâches pour intercepter les exceptions que vous pouvez gérer.  Étant donné que le prolongement des tâches fonctionne toujours, envisagez s'il faut ajouter un prolongement des tâches à la fin de la chaîne de prolongement.  Cela peut permettre de vous assurer que votre code considère toutes les exceptions.  L'exemple suivant illustre une chaîne simple de prolongation basée sur la valeur.  La troisième tâche dans les lancés de chaine, et par conséquent n'importe quel prolongement basé sur la valeur qui la suivent ne sont pas exécutés.  Toutefois, le dernier prolongement est basé sur des tâches, et par conséquent s'exécute toujours.  Le dernier prolongement gère l'exception lancée par la troisième tâche.  
  
 Nous recommandons que vous interceptiez des exceptions aussi spécifiques que possible.  Vous pouvez omettre le prolongement basé sur les tâches si vous n'avez pas d'exceptions spécifiques à intercepter.  Toute exception restera non prise en charge et peut mettre fin à l'application.  
  
 [!code-cpp[concrt-eh-task-chain#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_3.cpp)]  
  
> [!TIP]
>  Vous pouvez utiliser la méthode [concurrency::task\_completion\_event::set\_exception](../../parallel/concrt/reference/task-completion-event-class.md) pour associer une exception avec un événement d'exécution de la tâche.  Le document [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md) décrit plus en détail la classe [concurrency::task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md) .  
  
 [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) est un type d'exception runtime important qui sont liées à `task`.  Le runtime enlève `task_canceled` lorsque vous appelez `task::get` et cette tâche est annulée. \(En revanche, `task::wait` retourne [task\_status::canceled](../Topic/task_group_status%20Enumeration.md) et ne lève pas une exception.\) Vous pouvez repérer et gérer cette exception d'un prolongement basé sur les tâches ou lorsque vous appelez `task::get`.  Pour plus d'informations sur l'annulation des tâches , consultez [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
> [!CAUTION]
>  N'enlevez jamais `task_canceled` de votre code.  Appel [concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md) à la place.  
  
 Le runtime termine l'application si une tâche lève une exception et que cette exception n'est pas interceptée par la tâche, une de ses procédures suivantes ou l'application principale.  Si votre application se bloque, vous pouvez configurer Visual Studio pour arrêter lorsque des exceptions C\+\+ sont levées.  Après avoir diagnostiqué l'emplacement de l'exception non gérée, utilisez un prolongement basé sur les tâches pour la gérer.  
  
 La section [Exceptions Levées par le runtime](#runtime) dans ce document explique comment travailler avec des exceptions d'exécution plus en détail.  
  
 \[[Premières](#top)\]  
  
##  <a name="task_groups"></a> Groupes de tâches et algorithmes parallèles  
 Cette section décrit comment le runtime gère les exceptions levées par des groupes de tâches.  Cette section s'applique également aux algorithmes parallèles tels que [concurrency::parallel\_for](../Topic/parallel_for%20Function.md), car ces algorithmes reposent sur les groupes de tâches.  
  
> [!CAUTION]
>  Assurez\-vous de comprendre les effets des exceptions sur les tâches dépendantes.  Pour les méthodes recommandées sur la gestion des exceptions des tâches ou des algorithmes parallèles, consultez la section " [Comprendre comment l'annulation et la gestion des exceptions affectent la destruction des objets](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) section des meilleures pratiques dans la rubrique de bibliothèque de modèles parallèles.  
  
 Pour plus d'informations sur les groupes de tâches, consultez [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  Pour plus d'informations sur les algorithmes parallèles, consultez [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
 Lorsque vous levez une exception dans le corps d'une fonction de travail que vous passez à un objet [concurrency::task\_group](../Topic/task_group%20Class.md) ou [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md), le runtime stocke cette exception et la marshale au contexte qui appelle [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) ou [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md).  Le runtime arrête également toutes les tâches actives qui sont dans le groupe de tâches \(y compris celles des groupes de tâches enfants\) et ignore toutes les tâches qui n'ont pas encore démarré.  
  
 L'exemple suivant montre la structure de base d'une fonction de travail qui lève une exception.  L'exemple utilise un objet `task_group` pour imprimer les valeurs de deux objets `point` en parallèle.  La fonction de travail `print_point` imprime les valeurs d'un objet `point` sur la console.  La fonction de travail lève une exception si la valeur d'entrée est `NULL`.  Le runtime stocke cette exception et la marshale au contexte qui appelle `task_group::wait`.  
  
 [!code-cpp[concrt-eh-task-group#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_4.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **X \= 15, Y \= 30**  
**Exception interceptée : point est NULL.** Pour obtenir un exemple complet qui utilise la gestion des exceptions dans un groupe de tâches, consultez [Comment : utiliser la gestion des exceptions pour rompre une boucle parallèle](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="runtime"></a> Exceptions levées par le runtime  
 Une exception peut résulter d'un appel au runtime.  La plupart des types d'exception, exceptés [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) et [concurrency::operation\_timed\_out](../../parallel/concrt/reference/operation-timed-out-class.md), indiquent une erreur de programmation.  Ces erreurs sont en général irrécupérables, et par conséquent ne doivent être ni interceptées ni gérées par le code d'application.  Nous vous suggérons d'intercepter ou de gérer les erreurs irrécupérables dans votre code d'application uniquement lorsque vous devez diagnostiquer des erreurs de programmation.  Toutefois, la connaissance des types d'exceptions définis par le runtime peut vous aider à diagnostiquer les erreurs de programmation.  
  
 Le mécanisme de gestion des exceptions est identique pour les exceptions levées par le runtime et pour celles levées par des fonctions de travail.  Par exemple, la fonction [concurrency::receive](../Topic/receive%20Function.md) enlève `operation_timed_out` lorsqu'elle ne reçoit pas de message durant la période spécifiée.  Si `receive` lève une exception dans une fonction de travail que vous passez à un groupe de tâches, le runtime stocke cette exception et la marshale au contexte qui appelle `task_group::wait`, `structured_task_group::wait`, `task_group::run_and_wait` ou `structured_task_group::run_and_wait`.  
  
 L'exemple suivant utilise l'algorithme [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) pour exécuter deux tâches en parallèle.  La première tâche attend cinq secondes, puis envoie un message vers un tampon de messages.  La deuxième tâche utilise la fonction `receive` pour attendre pendant trois secondes de recevoir un message du même tampon de messages.  La fonction `receive` lève `operation_timed_out` si elle ne reçoit pas le message dans le délai imparti.  
  
 [!code-cpp[concrt-eh-time-out#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_5.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **L'opération a expiré.** Pour empêcher tout arrêt anormal de votre application, assurez\-vous que votre code gère les exceptions lorsqu'il fait appel au runtime.  Gérez également les exceptions lorsque vous appelez du code externe qui utilise le runtime d'accès concurrentiel, par exemple une bibliothèque tierce.  
  
 \[[Premières](#top)\]  
  
##  <a name="multiple"></a> Exceptions multiples  
 Si une tâche ou un algorithme parallèle reçoit plusieurs exceptions, le runtime marshale une seule de ces exceptions au contexte appelant.  Le runtime ne garantit pas quelle exception il marshale.  
  
 L'exemple suivant utilise l'algorithme `parallel_for` pour imprimer des nombres sur la console.  Il lève une exception si la valeur d'entrée est inférieure à une certaine valeur minimale ou supérieure à une certaine valeur maximale.  Dans cet exemple, plusieurs fonctions de travail peuvent lever une exception.  
  
 [!code-cpp[concrt-eh-multiple#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_6.cpp)]  
  
 Voici un exemple de sortie pour cet exemple.  
  
  **8**  
**2**  
**9**  
**3**  
**10**  
**4**  
**5**  
**6**  
**7**  
**Exception interceptée : \-5 : la valeur est inférieure à la valeur minimale.** \[[Premières](#top)\]  
  
##  <a name="cancellation"></a> Annulation  
 Les exceptions n'indiquent pas toutes une erreur.  Par exemple, un algorithme de recherche peut utiliser la gestion des exceptions pour arrêter sa tâche associée lorsqu'il trouve le résultat.  Pour plus d'informations sur la façon d'utiliser des mécanismes d'annulation dans votre code, consultez [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="lwts"></a> Tâches légères  
 Une tâche légère est une tâche que vous planifiez directement à partir d'un objet [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md).  Les tâches légères présentent des charges inférieures aux tâches ordinaires.  En revanche, le runtime n'intercepte pas les exceptions levées par des tâches légères.  Au lieu de cela, l'exception est interceptée par le gestionnaire d'exceptions non gérée, qui par défaut met fin au processus.  Par conséquent, vous devez utiliser un mécanisme de gestion des erreurs approprié dans votre application.  Pour plus d'informations sur les tâches légères, consultez [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="agents"></a> Agents asynchrones  
 Comme les tâches légères, le runtime ne gère pas les exceptions levées par les agents asynchrones.  
  
 L'exemple suivant illustre une manière de gérer les exceptions dans une classe qui dérive de [concurrency::agent](../../parallel/concrt/reference/agent-class.md).  Cet exemple définit la classe `points_agent`.  La méthode `points_agent::run` lit les objets `point` à partir du tampon de messages et les imprime sur la console.  La méthode `run` lève une exception si elle reçoit un pointeur `NULL`.  
  
 La méthode `run` entoure tout le travail dans un bloc `try`\-`catch`.  Le bloc `catch` stocke l'exception dans un tampon de messages.  L'application vérifie si l'agent a rencontré une erreur en lisant cette mémoire tampon une fois que l'agent a terminé.  
  
 [!code-cpp[concrt-eh-agents#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_7.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **X : 10, Y : 20**  
**X : 20, Y : 30**  
**erreur s'est produite dans l'agent : le point ne doit pas avoir la valeur NULL**  
**l'état de l'agent est : fait** Étant donné que le bloc `try`\-`catch` existe à l'extérieur de la boucle `while`, l'agent met fin au traitement lorsqu'il rencontre la première erreur.  Si le bloc `try`\-`catch` se trouvait à l'intérieur de la boucle `while`, l'agent continuerait après qu'une erreur se soit produite.  
  
 Cet exemple stocke les exceptions dans un tampon de messages afin qu'un autre composant puisse surveiller la présence éventuelle d'erreurs sur l'agent lors de son exécution.  Cet exemple utilise un objet [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md) pour stocker l'erreur.  Dans le cas où un agent gère plusieurs exceptions, la classe `single_assignment` stocke uniquement le premier message qui lui est passé.  Pour stocker uniquement la dernière exception, utilisez la classe [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md).  Pour stocker toutes les exceptions, utilisez la classe [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md).  Pour plus d'informations sur ces blocs de messages, consultez [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 Pour plus d'informations sur les agents asynchrones, consultez [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="summary"></a> Résumé  
 \[[Premières](#top)\]  
  
## Voir aussi  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)   
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)