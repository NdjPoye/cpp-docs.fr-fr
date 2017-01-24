---
title: "task_options, classe (runtime d&#39;acc&#232;s concurrentiel) | Microsoft Docs"
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
  - "ppltasks/concurrency::task_options"
dev_langs: 
  - "C++"
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 7
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_options, classe (runtime d&#39;acc&#232;s concurrentiel)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente les options autorisées pour créer une tâche  
  
## Syntaxe  
  
```  
class task_options;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_options::task\_options, constructeur \(runtime d'accès concurrentiel\)](../Topic/task_options::task_options%20Constructor%20\(Concurrency%20Runtime\).md)|Surchargé.  Liste par défaut des options de création de tâches|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_options::get\_cancellation\_token, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::get_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|Retourne le jeton d'annulation.|  
|[task\_options::get\_continuation\_context, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::get_continuation_context%20Method%20\(Concurrency%20Runtime\).md)|Retourne le contexte de continuation|  
|[task\_options::get\_scheduler, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::get_scheduler%20Method%20\(Concurrency%20Runtime\).md)|Retourne le planificateur|  
|[task\_options::has\_cancellation\_token, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::has_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|Indique si un jeton d'annulation a été spécifié par l'utilisateur|  
|[task\_options::has\_scheduler, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::has_scheduler%20Method%20\(Concurrency%20Runtime\).md)|Indique si un planificateur n a été spécifié par l'utilisateur|  
|[task\_options::set\_cancellation\_token, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::set_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|Définit le jeton donné dans les options|  
|[task\_options::set\_continuation\_context, méthode \(runtime d'accès concurrentiel\)](../Topic/task_options::set_continuation_context%20Method%20\(Concurrency%20Runtime\).md)|Définit le contexte de continuation donné dans les options|  
  
## Hiérarchie d'héritage  
 `task_options`  
  
## Configuration requise  
 **En\-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)