---
title: "Instances de planificateur | Microsoft Docs"
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
  - "instances de planificateur"
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Instances de planificateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit le rôle des instances du planificateur dans le runtime d'accès concurrentiel. Il explique également comment utiliser les classes [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) et [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) pour créer et gérer des instances du planificateur.  Les instances du planificateur sont utiles lorsque vous souhaitez associer des stratégies de planification explicites à des types spécifiques de charge de travail.  Par exemple, vous pouvez créer une instance du planificateur pour effectuer certaines tâches avec une priorité de thread élevée et utiliser le planificateur par défaut pour effectuer d'autres tâches avec une priorité de thread normale.  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut. Par conséquent, vous n'êtes pas tenu d'en créer un dans votre application.  Étant donné que le planificateur de tâches vous aide à affiner les performances de vos applications, nous vous recommandons de commencer avec la [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md) ou la [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) si vous ne connaissez pas encore le runtime d'accès concurrentiel.  
  
##  <a name="top"></a> Sections  
  
-   [Classes Scheduler et CurrentScheduler](#classes)  
  
-   [Création d'une instance du planificateur](#creating)  
  
-   [Gestion de la durée de vie d'une instance du planificateur](#managing)  
  
-   [Méthodes et fonctionnalités](#features)  
  
-   [Exemple](#example)  
  
##  <a name="classes"></a> Classes Scheduler et CurrentScheduler  
 Le Planificateur de tâches permet aux applications d'utiliser une ou plusieurs *instances du planificateur* pour planifier le travail.  La classe [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) représente une instance du planificateur et encapsule la fonctionnalité liée à la planification des tâches.  
  
 Un thread joint à un planificateur porte le nom de *contexte d'exécution*, ou simplement de *contexte*.  Un seul planificateur peut être actif sur le contexte actuel à tout moment.  Le planificateur actif porte également le nom de *planificateur actuel*.  Le runtime d'accès concurrentiel utilise la classe [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) pour fournir l'accès au planificateur actuel.  Le planificateur actuel d'un contexte peut différer du planificateur actuel d'un autre contexte.  Le runtime ne fournit pas de représentation au niveau processus du planificateur actuel.  
  
 En général, la classe `CurrentScheduler` est utilisée pour accéder au planificateur actuel.  La classe `Scheduler` est utile lorsque vous devez exécuter un planificateur qui n'est pas le planificateur actuel.  
  
 Les sections suivantes décrivent comment créer et gérer une instance du planificateur.  Pour obtenir un exemple complet qui illustre ces tâches, consultez [Comment : gérer une instance de planificateur](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="creating"></a> Création d'une instance du planificateur  
 Il existe trois manières de créer un objet `Scheduler` :  
  
-   S'il n'existe aucun planificateur, le runtime crée un planificateur par défaut lorsque vous utilisez une fonctionnalité de runtime, par exemple un algorithme parallèle, pour exécuter un travail.  Le planificateur par défaut devient le planificateur actuel du contexte qui initie le travail parallèle.  
  
-   La méthode [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md) crée un objet `Scheduler` qui utilise une stratégie spécifique et associe ce planificateur au contexte actuel.  
  
-   La méthode [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) crée un objet `Scheduler` qui utilise une stratégie spécifique, mais ne l'associe pas au contexte actuel.  
  
 Autoriser le runtime à créer un planificateur par défaut permet à toutes les tâches simultanées de partager le même planificateur.  Les fonctionnalités fournies par la [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md) \(PPL\) ou la [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) sont généralement utilisées pour exécuter un travail parallèle.  Par conséquent, vous n'êtes pas obligé de travailler directement avec le planificateur pour contrôler sa stratégie ou sa durée de vie.  Lorsque vous utilisez la Bibliothèque PPL ou la Bibliothèque d'agents, le runtime crée le planificateur par défaut s'il n'existe pas et fait de lui le planificateur actuel pour chaque contexte.  Lorsque vous créez un planificateur et que vous le définissez comme planificateur actuel, le runtime utilise ce planificateur pour planifier des tâches.  Créez d'autres instances du planificateur uniquement lorsque vous avez besoin d'une stratégie de planification spécifique.  Pour plus d'informations sur les stratégies associées à un planificateur, consultez [Stratégies de planificateur](../../parallel/concrt/scheduler-policies.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="managing"></a> Gestion de la durée de vie d'une instance du planificateur  
 Le runtime utilise un mécanisme de décompte de références pour contrôler la durée de vie des objets `Scheduler`.  
  
 Lorsque vous utilisez la méthode `CurrentScheduler::Create` ou `Scheduler::Create` pour créer un objet `Scheduler`, le runtime affecte la valeur « un » au décompte de références initial de ce planificateur.  Le runtime incrémente le décompte de références lorsque vous appelez la méthode [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md).  La méthode `Scheduler::Attach` associe l'objet `Scheduler` au contexte actuel.  Cela fait de lui le planificateur actuel.  Lorsque vous appelez la méthode `CurrentScheduler::Create`, le runtime crée un objet `Scheduler` et l'attache au contexte actuel \(et affecte la valeur « un » au décompte de références\).  Vous pouvez également utiliser la méthode [concurrency::Scheduler::Reference](../Topic/Scheduler::Reference%20Method.md) pour incrémenter le décompte de références d'un objet `Scheduler`.  
  
 Le runtime décrémente le décompte de références lorsque vous appelez la méthode [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) pour détacher le planificateur actuel, ou lorsque vous appelez la méthode [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md).  Lorsque le décompte de références atteint zéro, le runtime détruit l'objet `Scheduler` une fois toutes les tâches planifiées terminées.  Une tâche en cours d'exécution est autorisée à incrémenter le décompte de références du planificateur actuel.  Par conséquent, si le décompte de références atteint zéro et qu'une tâche l'incrémente, le runtime ne détruit l'objet `Scheduler` que lorsque le décompte de références atteint de nouveau la valeur zéro et que toutes les tâches sont terminées.  
  
 Le runtime conserve une pile interne d'objets `Scheduler` pour chaque contexte.  Lorsque vous appelez la méthode `Scheduler::Attach` ou `CurrentScheduler::Create`, le runtime pousse cet objet `Scheduler` sur la pile pour le contexte actuel.  Cela fait de lui le planificateur actuel.  Lorsque vous appelez `CurrentScheduler::Detach`, le runtime dépile le planificateur actuel de la pile pour le contexte actuel et définit le précédent comme planificateur actuel.  
  
 Le runtime offre plusieurs manières de gérer la durée de vie d'une instance du planificateur.  Le tableau suivant indique la méthode appropriée qui libère ou détache le planificateur du contexte actuel pour chaque méthode qui crée ou attache un planificateur au contexte actuel.  
  
|Méthode de création ou d'attachement|Méthode de libération ou de détachement|  
|------------------------------------------|---------------------------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 L'appel de la méthode de libération ou de détachement inappropriée produit un comportement non spécifié dans le runtime.  
  
 Lorsque vous utilisez une fonctionnalité, par exemple la Bibliothèque PPL, qui fait en sorte que le runtime crée pour votre compte le planificateur par défaut, vous ne devez ni libérer ni détacher ce planificateur.  Le runtime gère la durée de vie de tout planificateur qu'il crée.  
  
 Étant donné que le runtime ne détruit pas l'objet `Scheduler` avant que toutes les tâches ne soient terminées, vous pouvez utiliser la méthode [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md) ou la méthode [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md) pour recevoir une notification lorsqu'un objet `Scheduler` est détruit.  Ceci est utile lorsque vous devez attendre la fin de chaque tâche planifiée par un objet `Scheduler`.  
  
 \[[Premières](#top)\]  
  
##  <a name="features"></a> Méthodes et fonctionnalités  
 Cette section récapitule les méthodes importantes des classes `Scheduler` et `CurrentScheduler`.  
  
 Pensez à la classe `CurrentScheduler` comme un programme d'assistance à la création d'un planificateur à utiliser sur le contexte actuel.  La classe `Scheduler` vous permet de contrôler un planificateur qui appartient à un autre contexte.  
  
 Le tableau suivant répertorie les méthodes importantes définies par la classe `CurrentScheduler`.  
  
|Méthode|Description|  
|-------------|-----------------|  
|[Créer](../Topic/CurrentScheduler::Create%20Method.md)|Crée un objet `Scheduler` qui utilise la stratégie spécifiée et l'associe au contexte actuel.|  
|[Get](../Topic/CurrentScheduler::Get%20Method.md)|Extrait un pointeur vers l'objet `Scheduler` associé au contexte actuel.  Cette méthode n'incrémente pas le décompte de références de l'objet `Scheduler`.|  
|[Détacher](../Topic/CurrentScheduler::Detach%20Method.md)|Détache le planificateur actuel du contexte actuel et définit le précédent comme planificateur actuel.|  
|[RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|Enregistre un événement que le runtime définit lorsque le planificateur actuel est détruit.|  
|[CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|Crée un objet [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) dans le planificateur actuel.|  
|[ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|Ajoute une tâche légère à la file d'attente de planification du planificateur actuel.|  
|[GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md)|Extrait une copie de la stratégie associée au planificateur actuel.|  
  
 Le tableau suivant répertorie les méthodes importantes définies par la classe `Scheduler`.  
  
|Méthode|Description|  
|-------------|-----------------|  
|[Créer](../Topic/Scheduler::Create%20Method.md)|Crée un objet `Scheduler` qui utilise la stratégie spécifiée.|  
|[Attacher](../Topic/Scheduler::Attach%20Method.md)|Associe l'objet `Scheduler` au contexte actuel.|  
|[Référence](../Topic/Scheduler::Reference%20Method.md)|Incrémente le compteur de références de l'objet `Scheduler`.|  
|[Release](../Topic/Scheduler::Release%20Method.md)|Décrémente le compteur de références de l'objet `Scheduler`.|  
|[RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|Enregistre un événement que le runtime définit lorsque l'objet `Scheduler` est détruit.|  
|[CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|Crée un objet [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) dans l'objet `Scheduler`.|  
|[ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md)|Planifie une tâche légère à partir de l'objet `Scheduler`.|  
|[GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md)|Extrait une copie de la stratégie associée à l'objet `Scheduler`.|  
|[SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|Définit la stratégie que le runtime doit utiliser lors de la création du planificateur par défaut.|  
|[ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|Restaure la stratégie par défaut à celle qui était active avant l'appel à `SetDefaultSchedulerPolicy`.  Si le planificateur par défaut est créé après cet appel, le runtime utilise les paramètres de stratégie par défaut pour créer le planificateur.|  
  
 \[[Premières](#top)\]  
  
##  <a name="example"></a> Exemple  
 Pour obtenir des exemples de base sur la création et la gestion d'une instance du planificateur, consultez [Comment : gérer une instance de planificateur](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
## Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Comment : gérer une instance de planificateur](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Stratégies de planificateur](../../parallel/concrt/scheduler-policies.md)   
 [Groupes de planification](../../parallel/concrt/schedule-groups.md)