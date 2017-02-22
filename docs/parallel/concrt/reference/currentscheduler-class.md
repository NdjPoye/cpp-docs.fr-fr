---
title: "CurrentScheduler, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::CurrentScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CurrentScheduler (classe)"
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CurrentScheduler, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une abstraction pour le planificateur actuel associé au contexte d'appel.  
  
## Syntaxe  
  
```  
class CurrentScheduler;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CurrentScheduler::Create, méthode](../Topic/CurrentScheduler::Create%20Method.md)|Crée un nouveau planificateur dont le comportement est décrit par le paramètre `_Policy` et l'associe au contexte d'appel.  Le planificateur créé récemment deviendra le planificateur actuel pour le contexte d'appel.|  
|[CurrentScheduler::CreateScheduleGroup, méthode](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|Surchargé.  Crée un groupe de planification dans le planificateur associé au contexte d'appel.  La version qui accepte le paramètre `_Placement` entraîne des tâches au sein du nouveau groupe de planification créé un risque d'être influencé par rapport à l'exécution à l'emplacement spécifié par le paramètre.|  
|[CurrentScheduler::Detach, méthode](../Topic/CurrentScheduler::Detach%20Method.md)|Détache le planificateur actuel du contexte d'appel et restaure le planificateur précédemment associé comme planificateur actuel, le cas échéant.  Une fois que cette méthode a retourné une valeur, le contexte d'appel est géré par le planificateur précédemment attaché au contexte utilisant la méthode `CurrentScheduler::Create` ou `Scheduler::Attach`.|  
|[CurrentScheduler::Get, méthode](../Topic/CurrentScheduler::Get%20Method.md)|Retourne un pointeur au planificateur associé au contexte d'appel, également appelé planificateur actuel.|  
|[CurrentScheduler::GetNumberOfVirtualProcessors, méthode](../Topic/CurrentScheduler::GetNumberOfVirtualProcessors%20Method.md)|Retourne le nombre actuel de processeurs virtuels pour le planificateur associé au contexte d'appel.|  
|[CurrentScheduler::GetPolicy, méthode](../Topic/CurrentScheduler::GetPolicy%20Method.md)|Retourne une copie de la stratégie avec laquelle le planificateur actuel a été créé.|  
|[CurrentScheduler::Id, méthode](../Topic/CurrentScheduler::Id%20Method.md)|Retourne un identificateur unique pour le planificateur actuel.|  
|[CurrentScheduler::IsAvailableLocation, méthode](../Topic/CurrentScheduler::IsAvailableLocation%20Method.md)|Détermine si un emplacement spécifique est disponible sur le planificateur actuel.|  
|[CurrentScheduler::RegisterShutdownEvent, méthode](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|A pour effet de signaler le gestionnaire d'événements Windows passé dans le paramètre `_ShutdownEvent` lorsque le planificateur associé au contexte actuel s'arrête et s'autodétruit.  Au moment où l'événement est signalé, tout le travail qui avait été planifié par le planificateur est terminé.  Plusieurs événements d'arrêt peuvent être enregistrés via cette méthode.|  
|[CurrentScheduler::ScheduleTask, méthode](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|Surchargé.  Planifie une tâche légère dans le planificateur associé au contexte d'appel.  La tâche légère sera placée dans un groupe de planification déterminé par le runtime.  La version qui accepte le paramètre `_Placement` implique que la tâche soit influencée par rapport l'exécution à l'emplacement indiqué.|  
  
## Notes  
 S'il n'y a aucun planificateur \(consultez [Planificateur](../../../parallel/concrt/reference/scheduler-class.md)\) associé au contexte d'appel, de nombreuses méthodes dans la classe `CurrentScheduler` auront pour résultat d'associer le planificateur par défaut du processus.  Cela peut également impliquer que le planificateur par défaut du processus est créé pendant un tel appel.  
  
## Hiérarchie d'héritage  
 `CurrentScheduler`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler, classe](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)