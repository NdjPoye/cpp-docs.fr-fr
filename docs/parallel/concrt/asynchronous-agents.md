---
title: "Agents asynchrones | Microsoft Docs"
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
  - "agents (runtime d'accès concurrentiel)"
  - "agents asynchrones"
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
caps.latest.revision: 15
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Agents asynchrones
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un *agent asynchrone* \(ou simplement *agent*\) est un composant d'application qui opère de manière asynchrone avec d'autres agents afin d'effectuer de plus grandes tâches de calcul.  On peut considérer un agent comme une tâche qui a un cycle de vie fixe.  Par exemple, un agent peut lire des données d'un périphérique d'entrée\/sortie \(tel que le clavier, un fichier sur disque ou une connexion réseau\) et un autre agent peut exécuter une action sur ces données dès qu'elles deviennent disponibles.  Le premier agent utilise le passage de message pour signaler au deuxième agent que davantage de données sont disponibles.  Le planificateur de tâches du runtime d'accès concurrentiel fournit un mécanisme efficace pour permettre aux agents de se bloquer et de céder de manière coopérative sans nécessiter de préemption moins efficace.  
  
 La Bibliothèque d'agents définit la classe [concurrency::agent](../../parallel/concrt/reference/agent-class.md) pour représenter un agent asynchrone.  `agent` est une classe abstraite qui déclare la méthode virtuelle [concurrency::agent::run](../Topic/agent::run%20Method.md).  La méthode `run` exécute la tâche effectuée par l'agent.  La méthode `run` étant abstraite, vous devez l'implémenter dans chaque classe que vous dérivez d'`agent`.  
  
## Cycle de vie d'agent  
 Les agents ont un cycle de vie fixe.  L'énumération [concurrency::agent\_status](../Topic/agent_status%20Enumeration.md) définit les différents états d'un agent.  L'illustration suivante est un diagramme d'état qui montre comment les agents progressent d'un état à un autre.  Dans cette illustration, les traits pleins représentent des méthodes que vous appelez à partir de votre application ; les traits en pointillés représentent des méthodes appelées à partir du runtime.  
  
 ![Diagramme d'état de l'agent](../../parallel/concrt/media/agentstate.png "AgentState")  
  
 Le tableau suivant décrit chaque état dans l'énumération `agent_status`.  
  
|État d'agent|Description|  
|------------------|-----------------|  
|`agent_created`|L'exécution de l'agent n'a pas été planifiée.|  
|`agent_runnable`|Le runtime planifie l'exécution de l'agent.|  
|`agent_started`|L'agent a démarré et est en cours d'exécution.|  
|`agent_done`|L'agent a terminé.|  
|`agent_canceled`|L'agent a été annulé avant de passer à l'état `started`.|  
  
 `agent_created` est l'état initial d'un agent, `agent_runnable` et `agent_started` sont les états actifs, et `agent_done` et `agent_canceled` sont les états terminaux.  
  
 Utilisez la méthode [concurrency::agent::status](../Topic/agent::status%20Method.md) pour extraire l'état actuel d'un objet `agent`.  Bien que la méthode `status` soit sécurisée du point de vue de la concurrence, l'état de l'agent peut avoir changé au moment où la méthode `status` retourne.  Par exemple, un agent peut être à l'état `agent_started` quand vous appelez la méthode `status`, mais être passé à l'état `agent_done` juste après le retour de la méthode `status`.  
  
## Méthodes et fonctionnalités  
 Le tableau suivant montre quelques\-unes des méthodes importantes qui appartiennent à la classe `agent`.  Pour plus d'informations sur toutes les méthodes de la classe `agent`, consultez [agent, classe](../../parallel/concrt/reference/agent-class.md).  
  
|Méthode|Description|  
|-------------|-----------------|  
|[start](../Topic/agent::start%20Method.md)|Planifie l'objet `agent` pour l'exécution et le place à l'état `agent_runnable`.|  
|[run](../Topic/agent::run%20Method.md)|Exécute la tâche qui doit être effectuée par l'objet `agent`.|  
|[done](../Topic/agent::done%20Method.md)|Fait passer un agent à l'état `agent_done`.|  
|[cancel](../Topic/agent::cancel%20Method.md)|Si l'agent n'a pas été démarré, cette méthode annule l'exécution de l'agent et le place à l'état `agent_canceled`.|  
|[status](../Topic/agent::status%20Method.md)|Extrait l'état actuel de l'objet `agent`.|  
|[wait](../Topic/agent::wait%20Method.md)|Attend que l'objet `agent` passe à l'état `agent_done` ou `agent_canceled`.|  
|[wait\_for\_all](../Topic/agent::wait_for_all%20Method.md)|Attend que tous les objets `agent` fournis passent à l'état `agent_done` ou `agent_canceled`.|  
|[wait\_for\_one](../Topic/agent::wait_for_one%20Method.md)|Attend qu'au moins l'un des objets `agent` fournis passe à l'état `agent_done` ou `agent_canceled`.|  
  
 Après avoir créé un objet d'agent, appelez la méthode [concurrency::agent::start](../Topic/agent::start%20Method.md) pour planifier son exécution.  Le runtime appelle la méthode `run` après avoir planifié l'agent et le place à l'état `agent_runnable`.  
  
 Le runtime ne gère pas les exceptions levées par les agents asynchrones.  Pour plus d'informations sur la levée d'exceptions et les agents, consultez [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## Exemple  
 Pour obtenir un exemple qui indique comment créer une application de base basée sur agent, consultez [Procédure pas à pas : création d’une application basée sur un agent](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)