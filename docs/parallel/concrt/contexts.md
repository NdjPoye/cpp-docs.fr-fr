---
title: "Contextes | Microsoft Docs"
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
  - "contextes (runtime d'accès concurrentiel)"
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contextes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit le rôle des contextes dans le Runtime d’accès concurrentiel. Un thread qui est associé à un planificateur est appelé un *contexte d’exécution*, ou simplement *contexte*. Le [concurrency::wait](../Topic/wait%20Function.md) fonction et l’accès concurrentiel ::[classe du contexte](../../parallel/concrt/reference/context-class.md) vous permettent de contrôler le comportement des contextes. Utilisez le `wait` fonction interrompe le contexte actuel pendant une durée spécifiée. Utilisez la `Context` classe lorsque vous avez besoin de davantage de contrôle sur le moment contextes bloquent, débloquent et yield ou lorsque vous voulez surabonner le contexte actuel.  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut, et vous n'êtes donc pas obligé d'en créer un dans votre application. Étant donné que le Planificateur de tâches vous aide à optimiser les performances de vos applications, nous vous recommandons de commencer avec la [bibliothèque de modèles parallèles (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) ou [bibliothèque d’Agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) Si vous ne connaissez pas le Runtime d’accès concurrentiel.  
  
## <a name="the-wait-function"></a>L’attente (fonction)  
 Le [concurrency::wait](../Topic/wait%20Function.md) fonction cède de façon coopérative l’exécution du contexte actuel pendant un nombre spécifié de millisecondes. Le runtime utilise la durée de cession pour effectuer d’autres tâches. Une fois le délai spécifié écoulé, le runtime replanifie le contexte pour l’exécution. Par conséquent, le `wait` fonction peut interrompre le contexte actuel dépasse la valeur fournie pour le `milliseconds` paramètre.  
  
 Passer la valeur 0 (zéro) le `milliseconds` paramètre, le runtime interrompe le contexte actuel jusqu'à ce que tous les autres contextes actifs aient l’opportunité pour effectuer le travail. Cela vous permet de générer une tâche pour toutes les autres tâches actives.  
  
### <a name="example"></a>Exemple  
 Pour obtenir un exemple qui utilise le `wait` de fonction pour céder le contexte actuel et donc permettre à d’autres contextes d’exécution, consultez [Comment : utiliser des groupes de planification pour Influence ordre d’exécution](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="the-context-class"></a>La classe de contexte  
 L’accès concurrentiel ::[classe du contexte](../../parallel/concrt/reference/context-class.md) fournit une abstraction de programmation pour un contexte d’exécution et propose deux fonctionnalités importantes : la possibilité de bloquer, débloquer et céder le contexte actuel de manière coopérative et la capacité à surabonner le contexte actuel.  
  
### <a name="cooperative-blocking"></a>Blocage coopératif  
 La `Context` classe vous permet de bloquer ou de céder le contexte d’exécution actuel. Blocage ou la cession est utile lorsque le contexte actuel ne peut pas continuer car une ressource n’est pas disponible.  
  
 Le [Concurrency::Context :: Block](../Topic/Context::Block%20Method.md) méthode bloque le contexte actuel. Un contexte bloqué cède ses ressources de traitement afin que le runtime puisse effectuer d’autres tâches. Le [Concurrency::Context :: Unblock](../Topic/Context::Unblock%20Method.md) méthode débloque un contexte bloqué. Le `Context::Unblock` méthode doit être appelée à partir d’un contexte différent de celui qui a appelé `Context::Block`. Le runtime lève [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) Si un contexte tente de se débloquer.  
  
 Pour bloquer et débloquer un contexte de manière coopérative, vous appelez généralement [Concurrency::Context :: CurrentContext](../Topic/Context::CurrentContext%20Method.md) pour récupérer un pointeur vers le `Context` objet associé au thread en cours, puis enregistrer le résultat. Appelez ensuite la `Context::Block` méthode pour bloquer le contexte actuel. Plus tard, appelez `Context::Unblock` à partir d’un contexte distinct pour débloquer le contexte bloqué.  
  
 Vous devez faire correspondre chaque paire d’appels à `Context::Block` et `Context::Unblock`. Le runtime lève [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) lors de la `Context::Block` ou `Context::Unblock` méthode est appelée consécutivement sans un appel correspondant à l’autre méthode. Toutefois, vous n’avez pas à appeler `Context::Block` avant d’appeler `Context::Unblock`. Par exemple, si un contexte appelle `Context::Unblock` avant qu’un autre contexte appelle `Context::Block` pour le même contexte, ce contexte reste non bloqué.  
  
 Le [Concurrency::Context :: yield](../Topic/Context::Yield%20Method.md) méthode cède l’exécution afin que le runtime peut effectuer d’autres tâches et replanifier le contexte pour l’exécution. Lorsque vous appelez le `Context::Block` (méthode), le runtime ne replanifie pas le contexte.  
  
#### <a name="example"></a>Exemple  
 Pour obtenir un exemple qui utilise le `Context::Block`, `Context::Unblock`, et `Context::Yield` méthodes pour implémenter une classe de sémaphore coopérative, consultez [Comment : utiliser la classe Context pour implémenter un sémaphore coopératif](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
##### <a name="oversubscription"></a>Surabonnement  
 Le planificateur par défaut crée le même nombre de threads qu’il sont a de threads matériels disponibles. Vous pouvez utiliser *le surabonnement* pour créer des threads supplémentaires pour un thread matériel donné.  
  
 Pour les opérations nécessitant le surabonnement généralement n’évolue pas car elle introduit une charge supplémentaire. Toutefois, pour les tâches qui ont une quantité élevée de latence, par exemple, lire des données à partir du disque ou d’une connexion réseau, le surabonnement peut améliorer l’efficacité globale de certaines applications.  
  
> [!NOTE]
>  Activer le surabonnement uniquement à partir d’un thread qui a été créé par le Runtime d’accès concurrentiel. Le surabonnement n’a aucun effet lorsqu’elle est appelée à partir d’un thread qui n’a pas été créé par le runtime (y compris le thread principal).  
  
 Pour activer le surabonnement dans le contexte actuel, appelez le [Concurrency::Context :: Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) méthode avec la `_BeginOversubscription` paramètre la valeur `true`. Lorsque vous activez le surabonnement sur un thread qui a été créé par le Runtime d’accès concurrentiel, elle entraîne le runtime crée un thread supplémentaire. Une fois que toutes les tâches qui requièrent le surabonnement sont terminées, appelez `Context::Oversubscribe` avec la `_BeginOversubscription` paramètre la valeur `false`.  
  
 Vous pouvez activer le surabonnement plusieurs fois dans le contexte actuel, mais vous devez le désactiver le même nombre de fois que vous l’activez. Le surabonnement peut également être imbriqué ; Autrement dit, une tâche est créée par une autre tâche qui utilise le surabonnement peut également surabonner son contexte. Toutefois, si une tâche imbriquée et son parent appartiennent au même contexte, seul l’appel extérieur à `Context::Oversubscribe` provoque la création d’un thread supplémentaire.  
  
> [!NOTE]
>  Le runtime lève [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) Si le surabonnement est désactivé avant que cette option est activée.  
  
###### <a name="example"></a>Exemple  
 Pour obtenir un exemple qui utilise le surabonnement pour compenser la latence provoquée par la lecture des données à partir d’une connexion réseau, consultez [Comment : utiliser le surabonnement à la latence du décalage](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Comment : utiliser des groupes de planifications pour influencer l’ordre d’exécution](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)   
 [Comment : utiliser la classe Context pour implémenter un sémaphore coopératif](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Comment : utiliser le surabonnement pour compenser la latence](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

