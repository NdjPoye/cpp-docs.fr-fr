---
title: "task_completion_event, classe | Microsoft Docs"
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
  - "ppltasks/concurrency::task_completion_event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_completion_event (classe)"
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_completion_event, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `task_completion_event` vous permet de différer l'exécution d'une tâche jusqu'à ce qu'une condition soit remplie, ou de démarrer une tâche en réponse à un événement externe.  
  
## Syntaxe  
  
```  
template<  
   typename _ResultType  
>  
class task_completion_event;  
  
template<>  
class task_completion_event<void>;  
```  
  
#### Paramètres  
 `_ResultType`  
 Type de résultat de cette classe `task_completion_event`.  
  
 `T`  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_completion\_event::task\_completion\_event, constructeur](../Topic/task_completion_event::task_completion_event%20Constructor.md)|Construit un objet `task_completion_event`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_completion\_event::set, méthode](../Topic/task_completion_event::set%20Method.md)|Surchargé.  Définit l'événement d'achèvement de tâche.|  
|[task\_completion\_event::set\_exception, méthode](../Topic/task_completion_event::set_exception%20Method.md)|Surchargé.  Propage une exception à toutes les tâches associées à cet événement.|  
  
## Notes  
 Utilisez une tâche créée à partir d'un événement d'achèvement de tâche lorsque votre scénario requiert que vous créiez une tâche qui se terminer, et par conséquent, que ses continuations soient planifiées pour l'exécution, à un moment donné dans le futur.  La classe `task_completion_event` doit avoir le même type que la tâche que vous créez, et l'appel de la méthode Set sur l'événement d'achèvement de tâche avec une valeur de ce type provoquera l'exécution de la tâche associée, et fournir cette valeur à la suite de ses continuations.  
  
 Si l'événement d'achèvement de tâche n'est jamais signalé, toutes les tâches créées à partir de cette source seront annulées une fois détruite.  
  
 `task_completion_event` se comporte comme un pointeur intelligent, et doit être passé par valeur.  
  
## Hiérarchie d'héritage  
 `task_completion_event`  
  
## Configuration requise  
 **En\-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/fr-fr/5389e8a5-5038-40b6-844a-55e9b58ad35f)