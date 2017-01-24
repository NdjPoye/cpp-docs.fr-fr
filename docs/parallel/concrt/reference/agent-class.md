---
title: "agent, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::agent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "agent (classe)"
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# agent, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Classe prévue pour être utilisée comme une classe de base pour tous les agents indépendants.  Elle permet de masquer l'état d'autres agents et pour interagir grâce à le passage de message.  
  
## Syntaxe  
  
```  
class agent;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[agent::agent, constructeur](../Topic/agent::agent%20Constructor.md)|Surchargé.  Construit un agent.|  
|[agent::~agent, destructeur](../Topic/agent::~agent%20Destructor.md)|Détruit l'agent.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[agent::cancel, méthode](../Topic/agent::cancel%20Method.md)|Déplace un agent depuis les états `agent_created` ou `agent_runnable` vers l'état `agent_canceled`.|  
|[agent::start, méthode](../Topic/agent::start%20Method.md)|Déplace un agent de l'état `agent_created` vers l'état `agent_runnable` et le planifie pour l'exécution.|  
|[agent::status, méthode](../Topic/agent::status%20Method.md)|Source synchrone d'informations d'état de l'agent.|  
|[agent::status\_port, méthode](../Topic/agent::status_port%20Method.md)|Source asynchrone d'informations d'état de l'agent.|  
|[agent::wait, méthode](../Topic/agent::wait%20Method.md)|Attend qu'un agent ait terminé sa tâche.|  
|[agent::wait\_for\_all, méthode](../Topic/agent::wait_for_all%20Method.md)|Attend que tous les agents spécifiés aient terminé leurs tâches.|  
|[agent::wait\_for\_one, méthode](../Topic/agent::wait_for_one%20Method.md)|Attend qu'un des agents spécifiés ait terminé sa tâche.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[agent::done, méthode](../Topic/agent::done%20Method.md)|Déplace un agent dans l'état `agent_done`, en indiquant que l'agent a complété.|  
|[agent::run, méthode](../Topic/agent::run%20Method.md)|Représente la tâche principale d'un agent.  `run` doit être substitué dans une classe dérivée et spécifie ce que l'agent doit faire après avoir démarré.|  
  
## Notes  
 Pour plus d'informations, consultez [Agents asynchrones](../../../parallel/concrt/asynchronous-agents.md).  
  
## Hiérarchie d'héritage  
 `agent`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)