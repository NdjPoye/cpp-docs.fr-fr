---
title: "task_continuation_context, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_continuation_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_continuation_context (classe)"
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# task_continuation_context, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `task_continuation_context` vous permet de spécifier l'emplacement d'exécution d'une continuation.  Il est utile d'utiliser cette classe d'une application du Windows Store.  Pour les fenêtres autres que les fenêtres Windows Store, le contexte d'exécution de la continuation de tâche est déterminé par l'exécution, et n'est pas configurable.  
  
## Syntaxe  
  
```  
class task_continuation_context : public details::_ContextCallback;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_continuation\_context::use\_arbitrary, méthode](../Topic/task_continuation_context::use_arbitrary%20Method.md)|Crée un contexte de continuation de tâche qui permet au Runtime de choisir le contexte d'exécution pour une continuation.|  
|[task\_continuation\_context::use\_current, méthode](../Topic/task_continuation_context::use_current%20Method.md)|Retourne un objet de contexte de continuation de tâche qui représente le contexte d'exécution actuel.|  
|[task\_continuation\_context::use\_default, méthode](../Topic/task_continuation_context::use_default%20Method.md)|Crée le contexte de continuation de tâche par défaut.|  
  
## Hiérarchie d'héritage  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## Configuration requise  
 **En\-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/fr-fr/5389e8a5-5038-40b6-844a-55e9b58ad35f)