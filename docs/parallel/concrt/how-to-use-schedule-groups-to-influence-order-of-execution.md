---
title: "Comment&#160;: utiliser des groupes de planification pour influencer l’ordre d’ex&#233;cution | Microsoft Docs"
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
  - "groupes de planification, utiliser [Runtime d’accès concurrentiel]"
  - "utiliser des groupes de planification [Runtime d’accès concurrentiel]"
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser des groupes de planification pour influencer l’ordre d’ex&#233;cution
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans le runtime d'accès concurrentiel, l'ordre dans lequel les tâches sont planifiées est non déterministe.  Toutefois, vous pouvez utiliser des stratégies de planification pour influencer l'ordre dans lequel les tâches s'exécutent.  Cette rubrique indique comment utiliser des groupes de planification avec la stratégie du planificateur [concurrency::SchedulingProtocol](../Topic/PolicyElementKey%20Enumeration.md) pour influencer l'ordre dans lequel les tâches s'exécutent.  
  
 L'exemple exécute un ensemble de tâches à deux reprises, chaque fois avec une stratégie de planification différente.  Les deux stratégies limitent la quantité maximale de ressources de traitement à deux.  La première exécution utilise la stratégie `EnhanceScheduleGroupLocality` , qui est la stratégie par défaut, et la deuxième exécution utilise la stratégie `EnhanceForwardProgress`.  Selon la stratégie `EnhanceScheduleGroupLocality`, le planificateur exécute toutes les tâches dans un groupe de planification jusqu'à ce que chaque tâche se termine ou cède les ressources.  Selon la stratégie `EnhanceForwardProgress`, le planificateur passe au groupe de planification suivant selon le principe du tourniquet \(round\-robin\) après qu'une seule tâche s'est terminée ou a cédé les ressources.  
  
 Lorsque chaque groupe de planification contient des tâches connexes, la stratégie `EnhanceScheduleGroupLocality` provoque en général une amélioration des performances car la localité du cache est conservée entre les tâches.  La stratégie `EnhanceForwardProgress` permet aux tâches de progresser et est utile lorsque vous avez besoin d'une équité de planification parmi les groupes de planification.  
  
## Exemple  
 Cet exemple définit la classe `work_yield_agent`, qui dérive de [concurrency::agent](../../parallel/concrt/reference/agent-class.md).  La classe `work_yield_agent` exécute une unité de travail, cède le contexte actuel, puis exécute une autre unité de travail.  L'agent utilise la fonction [concurrency::wait](../Topic/wait%20Function.md) pour céder le contexte actuel de manière coopérative afin que d'autres contextes puissent s'exécuter.  
  
 Cet exemple crée quatre objets `work_yield_agent`.  Pour illustrer comment définir des stratégies du planificateur de façon à affecter l'ordre dans lequel les agents s'exécutent, l'exemple associe les deux premiers agents à un groupe de planification et les deux autres agents à un autre groupe de planification.  L'exemple utilise la méthode [concurrency::CurrentScheduler::CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) pour créer les objets [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md).  L'exemple exécute les quatre agents à deux reprises, chaque fois avec une stratégie de planification différente.  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/CPP/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Utilisation EnhanceScheduleGroupLocality…**  
**groupe 0, tâche 0 : premier anneau…**  
**groupe 0, tâche 1 : premier anneau…**  
**groupe 0, tâche 0 : attente…**  
**groupe 1, tâche 0 : premier anneau…**  
**groupe 0, tâche 1 : attente…**  
**groupe 1, tâche 1 : premier anneau…**  
**groupe 1, tâche 0 : attente…**  
**groupe 0, tâche 0 : deuxième anneau…**  
**groupe 1, tâche 1 : attente…**  
**groupe 0, tâche 1 : deuxième anneau…**  
**groupe 0, tâche 0 : fini…**  
**groupe 1, tâche 0 : deuxième anneau…**  
**groupe 0, tâche 1 : fini…**  
**groupe 1, tâche 1 : deuxième anneau…**  
**groupe 1, tâche 0 : fini…**  
**groupe 1, tâche 1 : fini…**  
**Utilisation EnhanceForwardProgress…**  
**groupe 0, tâche 0 : premier anneau…**  
**groupe 1, tâche 0 : premier anneau…**  
**groupe 0, tâche 0 : attente…**  
**groupe 0, tâche 1 : premier anneau…**  
**groupe 1, tâche 0 : attente…**  
**groupe 1, tâche 1 : premier anneau…**  
**groupe 0, tâche 1 : attente…**  
**groupe 0, tâche 0 : deuxième anneau…**  
**groupe 1, tâche 1 : attente…**  
**groupe 1, tâche 0 : deuxième anneau…**  
**groupe 0, tâche 0 : fini…**  
**groupe 0, tâche 1 : deuxième anneau…**  
**groupe 1, tâche 0 : fini…**  
**groupe 1, tâche 1 : deuxième anneau…**  
**groupe 0, tâche 1 : fini…**  
**groupe 1, tâche 1 : fini…** Les deux stratégies produisent la même séquence d'événements.  Toutefois, la stratégie qui utilise `EnhanceScheduleGroupLocality` démarre les deux agents qui font partie du premier groupe de planification avant de démarrer les agents qui font partie du second groupe.  La stratégie qui utilise `EnhanceForwardProgress` démarre un agent du premier groupe, puis démarre le premier agent du second groupe.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet `Visual Studio`, ou collez\-le dans un fichier nommé scheduling\-protocol.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc scheduling\-protocol.cpp**  
  
## Voir aussi  
 [Groupes de planification](../../parallel/concrt/schedule-groups.md)   
 [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)