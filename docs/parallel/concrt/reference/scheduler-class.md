---
title: "Scheduler, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::Scheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Scheduler (classe)"
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Scheduler, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une abstraction pour un planificateur de runtime d'accès concurrentiel.  
  
## Syntaxe  
  
```  
class Scheduler;  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[Scheduler::Scheduler, constructeur](../Topic/Scheduler::Scheduler%20Constructor.md)|Un objet de la classe `Scheduler` peut uniquement être créé à l'aide de méthodes de fabrique, ou implicitement.|  
|[Scheduler::~Scheduler, destructeur](../Topic/Scheduler::~Scheduler%20Destructor.md)|Un objet de la classe `Scheduler` est détruit implicitement lorsque toutes ses références externes cessent d'exister.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Scheduler::Attach, méthode](../Topic/Scheduler::Attach%20Method.md)|Attache le planificateur au contexte d'appel.  Une fois que cette méthode a retourné une valeur, le contexte d'appel est géré par le planificateur et ce dernier devient le planificateur actuel.|  
|[Scheduler::Create, méthode](../Topic/Scheduler::Create%20Method.md)|Crée un nouveau planificateur dont le comportement est décrit par le paramètre `_Policy`, place une référence initiale sur le planificateur et retourne un pointeur vers celui\-ci.|  
|[Scheduler::CreateScheduleGroup, méthode](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|Surchargé.  Crée un groupe de planification dans le planificateur.  The version that takes the parameter `_Placement` causes tasks within the newly created schedule group to be biased towards executing at the location specified by that parameter.|  
|[Scheduler::GetNumberOfVirtualProcessors, méthode](../Topic/Scheduler::GetNumberOfVirtualProcessors%20Method.md)|Retourne le nombre actuel de processeurs virtuels pour le planificateur.|  
|[Scheduler::GetPolicy, méthode](../Topic/Scheduler::GetPolicy%20Method.md)|Retourne une copie de la stratégie avec laquelle le planificateur a été créé.|  
|[Scheduler::Id, méthode](../Topic/Scheduler::Id%20Method.md)|Retourne un identificateur unique pour le planificateur.|  
|[Scheduler::IsAvailableLocation, méthode](../Topic/Scheduler::IsAvailableLocation%20Method.md)|Détermine si un emplacement spécifique est disponible sur le planificateur.|  
|[Scheduler::Reference, méthode](../Topic/Scheduler::Reference%20Method.md)|Incrémente le nombre de références du planificateur.|  
|[Scheduler::RegisterShutdownEvent, méthode](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|A pour effet de signaler le gestionnaire d'événements Windows passé dans le paramètre `_Event` lorsque le planificateur s'arrête et s'autodétruit.  Au moment où l'événement est signalé, tout le travail qui avait été planifié par le planificateur est terminé.  Plusieurs événements d'arrêt peuvent être enregistrés via cette méthode.|  
|[Scheduler::Release, méthode](../Topic/Scheduler::Release%20Method.md)|Décrémente ce décompte de références de planificateur.|  
|[Scheduler::ResetDefaultSchedulerPolicy, méthode](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|Réinitialise la stratégie du planificateur au runtime par défaut.  La prochaine fois qu'un planificateur par défaut sera créé, il utilisera les paramètres de stratégie par défaut du runtime.|  
|[Scheduler::ScheduleTask, méthode](../Topic/Scheduler::ScheduleTask%20Method.md)|Surchargé.  Planifie une tâche légère dans le planificateur.  La tâche légère sera placée dans un groupe de planification déterminé par le runtime.  La version qui accepte le paramètre `_Placement` implique que la tâche soit influencé par rapport l'exécution à l'emplacement indiqué.|  
|[Scheduler::SetDefaultSchedulerPolicy, méthode](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|Autorise l'utilisation d'une stratégie définie par l'utilisateur pour créer le planificateur par défaut.  Cette méthode peut être appelée uniquement lorsque aucun planificateur par défaut n'existe dans le processus.  Après qu'une stratégie par défaut soit définie, elle reste en vigueur jusqu'au prochain appel valide de la méthode `SetDefaultSchedulerPolicy` ou [ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md).|  
  
## Notes  
 Le planificateur de runtime d'accès concurrentiel utilise des contextes d'exécution, qui sont mappés aux contextes d'exécution d'un système d'exploitation, tels qu'un thread, pour exécuter le travail mis en file d'attente par votre application sur le planificateur.  À tout moment, le niveau d'accès concurrentiel d'un planificateur est égal au nombre de processeurs virtuels qui lui sont accordés par le Gestionnaire des ressources.  Un processeur virtuel est une représentation abstraite d'une ressource de traitement qui mappe à un thread matériel dans le système sous\-jacent.  Seul un contexte de planificateur unique peut s'exécuter sur un processeur virtuel à un moment donné.  
  
 Le runtime d'accès concurrentiel créera un planificateur par défaut par processus pour exécuter le travail parallèle.  De plus vous pouvez créer vos propres instances du planificateur et les manipuler à l'aide de cette classe.  
  
## Hiérarchie d'héritage  
 `Scheduler`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler Class](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey, énumération](../Topic/PolicyElementKey%20Enumeration.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)