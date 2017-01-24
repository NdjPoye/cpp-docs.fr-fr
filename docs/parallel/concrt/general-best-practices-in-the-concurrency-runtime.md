---
title: "Meilleures pratiques en g&#233;n&#233;ral du runtime d’acc&#232;s concurrentiel | Microsoft Docs"
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
  - "runtime d’accès concurrentiel, meilleures pratiques générales"
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Meilleures pratiques en g&#233;n&#233;ral du runtime d’acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit les meilleures pratiques à appliquer à plusieurs zones du runtime d'accès concurrentiel.  
  
##  <a name="top"></a> Sections  
 Ce document contient les sections suivantes :  
  
-   [Utiliser les éléments de synchronisation coopérative, dans la mesure du possible](#synchronization)  
  
-   [Éviter les tâches longues qui ne cèdent pas](#yield)  
  
-   [Utiliser le surabonnement pour compenser les opérations qui effectuent un blocage ou qui présentent une latence élevée](#oversubscription)  
  
-   [Utiliser les fonctions de gestion de la mémoire simultanée, dans la mesure du possible](#memory)  
  
-   [Utiliser RAII pour gérer la durée de vie des objets d'accès concurrentiel](#raii)  
  
-   [Ne pas créer d'objets d'accès concurrentiel au niveau de la portée globale](#global-scope)  
  
-   [Ne pas utiliser d'objets d'accès concurrentiel dans les segments de données partagées](#shared-data)  
  
##  <a name="synchronization"></a> Utiliser les éléments de synchronisation coopérative, dans la mesure du possible  
 Le runtime d'accès concurrentiel fournit un grand nombre d'éléments sécurisés du point de vue de l'accès concurrentiel qui ne requièrent pas d'objet de synchronisation externe.  Par exemple, la classe [concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md) permet d'effectuer des opérations d'ajout et d'accès aux éléments sécurisées du point de vue de l'accès concurrentiel.  Toutefois, lorsque vous avez besoin d'un accès exclusif à une ressource, le runtime fournit les classes [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) et [concurrency::event](../../parallel/concrt/reference/event-class.md).  Ces types se comportent de manière coopérative. Par conséquent, le planificateur de tâches peut réallouer les ressources de traitement à un autre contexte pendant que la première tâche attend des données.  Si possible, utilisez ces types de synchronisation au lieu d'autres mécanismes de synchronisation, tels que ceux fournis par l'API Windows, qui ne se comportent pas de manière coopérative.  Pour plus d'informations sur ces types de synchronisation et pour obtenir un exemple de code, consultez [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md) et [Comparaison des structures de données de synchronisation avec l’API Windows](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="yield"></a> Éviter les tâches longues qui ne cèdent pas  
 Étant donné que le planificateur de tâches se comporte de manière coopérative, il ne traite pas équitablement les tâches.  Par conséquent, une tâche peut empêcher le démarrage d'autres tâches.  Dans certains cas, c'est acceptable. Dans d'autres cas, cela peut provoquer un interblocage ou la privation.  
  
 L'exemple suivant effectue plus de tâches que le nombre de ressources de traitement allouées.  La première tâche ne cède pas au planificateur de tâches. Par conséquent, la deuxième tâche ne démarre pas tant que la première n'est pas terminée.  
  
 [!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_1.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  
 Il existe plusieurs façons d'activer la coopération entre les deux tâches.  L'une des méthodes consiste à céder occasionnellement au planificateur de tâches lorsqu'une tâche met du temps à s'exécuter.  L'exemple suivant modifie la fonction `task` pour appeler la méthode [concurrency::Context::Yield](../Topic/Context::Yield%20Method.md) afin de céder l'exécution au planificateur de tâches et qu'une autre tâche puisse être exécutée.  
  
 [!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_2.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
  **1: 250000000**  
**2: 250000000**  
**1: 500000000**  
**2: 500000000**  
**1: 750000000**  
**2: 750000000**  
**1: 1000000000**  
**2: 1000000000** La méthode `Context::Yield` ne cède qu'à un autre thread actif dans le planificateur auquel le thread actuel appartient, à une tâche légère ou à un thread d'un système d'exploitation différent.  Cette méthode ne cède pas à un travail qui a été planifié pour s'exécuter dans un objet [concurrency::task\_group](../Topic/task_group%20Class.md) ou [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) qui n'a pas encore démarré.  
  
 Il existe d'autres façons d'activer la coopération entre des tâches de longue durée.  Vous pouvez scinder une grande tâche en sous\-tâches plus petites.  Vous pouvez également activer le surabonnement pendant une tâche de longue durée.  Le surabonnement vous permet de créer un nombre de threads plus important que le nombre de threads matériels disponibles.  Le surabonnement peut s'avérer particulièrement utile lorsqu'une tâche de longue durée présente une latence élevée, par exemple, lors de la lecture des données à partir d'un disque ou d'une connexion réseau.  Pour plus d'informations sur les tâches légères et le surabonnement, consultez [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="oversubscription"></a> Utiliser le surabonnement pour compenser les opérations qui effectuent un blocage ou qui présentent une latence élevée  
 Le runtime d'accès concurrentiel fournit des primitives de synchronisation, tel que [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md), qui permettent aux tâches d'effectuer un blocage de manière coopérative et de céder les unes aux autres.  Lorsqu'une tâche effectue un blocage ou cède de manière coopérative, le planificateur de tâches peut réaffecter les ressources de traitement à un autre contexte pendant que la première tâche attend des données.  
  
 Dans certains cas, vous ne pouvez pas utiliser le mécanisme de blocage coopératif qui est fourni par le runtime d'accès concurrentiel.  Par exemple, une bibliothèque externe que vous utilisez peut utiliser un mécanisme de synchronisation différent.  Ou encore, lorsque vous exécutez une opération qui peut présenter une latence élevée, par exemple lorsque vous utilisez la fonction `ReadFile` de l'API Windows pour lire des données à partir d'une connexion réseau.  Dans ces cas, le surabonnement peut permettre à des tâches de s'exécuter lorsqu'une autre tâche est inactive.  Le surabonnement vous permet de créer un nombre de threads plus important que le nombre de threads matériels disponibles.  
  
 Prenons la fonction suivante, `download`, qui télécharge le fichier à l'URL donnée.  Cet exemple utilise la méthode [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) pour augmenter provisoirement le nombre de threads actifs.  
  
 [!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_3.cpp)]  
  
 Étant donné que la fonction `GetHttpFile` effectue une opération potentiellement latente, le surabonnement peut permettre à d'autres tâches de s'exécuter pendant que la tâche actuelle attend des données.  Pour obtenir la version complète de cet exemple, consultez [Comment : utiliser le surabonnement pour compenser la latence](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="memory"></a> Utiliser les fonctions de gestion de la mémoire simultanée, dans la mesure du possible  
 Utilisez les fonctions de gestion de la mémoire, [concurrency::Alloc](../Topic/Alloc%20Function.md) et [concurrency::Free](../Topic/Free%20Function.md), en présence de tâches de granularité fine qui allouent souvent des petits objets dont la durée de vie est relativement courte.  Le runtime d'accès concurrentiel maintient un cache mémoire séparé pour chaque thread en cours de exécution.  Les fonctions `Alloc` et `Free` allouent et libèrent la mémoire disponible de ces caches sans utiliser de verrous ou de barrières de mémoire.  
  
 Pour plus d'informations sur ces fonctions de gestion de la mémoire, consultez [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  Pour obtenir un exemple qui utilise ces fonctions, consultez [Comment : utiliser Alloc et Free pour améliorer les performances de la mémoire](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="raii"></a> Utiliser RAII pour gérer la durée de vie des objets d'accès concurrentiel  
 Le runtime d'accès concurrentiel utilise la gestion des exceptions pour implémenter des fonctionnalités telles que l'annulation.  Par conséquent, écrivez du code sécurisé du point de vue des exceptions lorsque vous appelez le runtime ou une autre bibliothèque qui appelle le runtime.  
  
 Le modèle *RAII* \(Resource Acquisition Is Initialization\) est un moyen de gérer sans risque la durée de vie d'un objet d'accès concurrentiel dans une portée donnée.  Selon le modèle RAII, une structure de données est allouée sur la pile.  Cette structure de données initialise ou acquiert une ressource lorsqu'elle est créée et détruit ou libère cette ressource lorsque la structure de données est détruite.  Le modèle RAII garantit que le destructeur est appelé avant que la portée englobante ne quitte.  Ce modèle est utile lorsqu'une fonction contient plusieurs instructions `return`.  Ce modèle est également utile lorsque vous écrivez du code sécurisé du point de vue des exceptions.  Lorsqu'une instruction `throw` provoque le déroulement de la pile, le destructeur de l'objet RAII est appelé. Par conséquent, la ressource est toujours correctement supprimée ou libérée.  
  
 Le runtime définit plusieurs classes qui utilisent le modèle RAII, par exemple, [concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md) et [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md).  Ces classes d'assistance portent le nom de *verrous à portée limitée*.  Ces classes procurent plusieurs avantages lorsque vous travaillez avec les objets [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) ou [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md).  Le constructeur de ces classes acquiert l'accès à l'objet `critical_section` ou `reader_writer_lock` fourni et le destructeur libère l'accès à cet objet.  Étant donné qu'un verrou à portée limitée libère automatiquement l'accès à son objet d'exclusion mutuelle lorsqu'il est détruit, vous ne déverrouillez pas l'objet sous\-jacent manuellement.  
  
 Prenons l'exemple de la classe suivante, `account`, qui est définie par une bibliothèque externe et ne peut donc pas être modifiée.  
  
 [!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_4.h)]  
  
 L'exemple suivant effectue plusieurs transactions sur un objet `account` en parallèle.  L'exemple utilise un objet `critical_section` pour synchroniser l'accès à l'objet `account`, car la classe `account` n'est pas sécurisée du point de vue de l'accès concurrentiel.  Chaque opération parallèle utilise un objet `critical_section::scoped_lock` pour garantir que l'objet `critical_section` est déverrouillé lorsque l'opération réussit ou échoue.  Lorsque le solde de compte est négatif, l'opération `withdraw` échoue en levant une exception.  
  
 [!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_5.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant :  
  
  **Solde avant dépôt : 1924**  
**Solde après dépôt : 2924**  
**Solde avant retrait : 2924**  
**Solde après retrait : \-76**  
**Solde avant retrait : \-76**  
**Détails de l'erreur :**  
 **solde négatif : \-76** Pour obtenir des exemples supplémentaires qui utilisent le modèle RAII pour gérer la durée de vie des objets d'accès concurrentiel, consultez [Procédure pas à pas : suppression de travail d'un thread d'interface utilisateur](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [Comment : utiliser la classe Context pour implémenter un sémaphore coopératif](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md) et [Comment : utiliser le surabonnement pour compenser la latence](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="global-scope"></a> Ne pas créer d'objets d'accès concurrentiel au niveau de la portée globale  
 Lorsque vous créez un objet de concurrence au niveau global vous pouvez déclencher des problèmes tels que des violations d'interblocage ou d'accès de mémoire de votre application.  
  
 Par exemple, lorsque vous créez un objet de runtime d'accès concurrentiel, le runtime crée un planificateur par défaut pour vous, si aucun planificateur n'existe déjà.  Objet de runtime créé pendant la construction d'objets globales forcera en conséquence le runtime à créer ce planificateur par défaut.  Toutefois, ce processus utilise un verrou interne, ce qui peut perturber l'initialisation d'autres objets qui prennent en charge l'infrastructure du runtime d'accès concurrentiel.  Ce verrou interne peut être requis par un autre objet d'infrastructure qui n'a pas encore été initialisé, et donc peut entraîner un interblocage dans votre application.  
  
 L'exemple suivant illustre la création d'un objet [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) global.  Ce modèle s'applique non seulement à la classe `Scheduler`, mais à tous les autres types fournis par le runtime d'accès concurrentiel.  Nous vous conseillons de ne pas respecter ce modèle, étant donné qu'il peut provoquer un comportement inattendu de votre application.  
  
 [!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_6.cpp)]  
  
 Pour obtenir des exemples sur la façon de créer correctement des objets `Scheduler`, consultez [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="shared-data"></a> Ne pas utiliser d'objets d'accès concurrentiel dans les segments de données partagées  
 Le runtime d'accès concurrentiel ne prend pas en charge l'utilisation d'objets d'accès concurrentiel dans une section de données partagées, par exemple, une section de données créée par la directive [data\_seg](../../preprocessor/data-seg.md) `#pragma`.  Un objet d'accès concurrentiel partagé au delà des limites de processus peut entraîner un état incohérent ou non valide du runtime.  
  
 \[[Premières](#top)\]  
  
## Voir aussi  
 [Meilleures pratiques sur le runtime d'accès concurrentiel](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md)   
 [Comparaison des structures de données de synchronisation avec l’API Windows](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)   
 [Comment : utiliser Alloc et Free pour améliorer les performances de la mémoire](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [Comment : utiliser le surabonnement pour compenser la latence](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [Comment : utiliser la classe Context pour implémenter un sémaphore coopératif](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Procédure pas à pas : suppression de travail d'un thread d'interface utilisateur](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [Meilleures pratiques de la Bibliothèque de modèles parallèles](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [meilleures pratiques pour la bibliothèque d’agents asynchrones](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)