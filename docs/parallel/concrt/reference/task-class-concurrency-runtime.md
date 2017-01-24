---
title: "task (Concurrency Runtime), classe | Microsoft Docs"
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
  - "ppltasks/concurrency::task"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task (classe)"
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task (Concurrency Runtime), classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Classe `task` de la bibliothèque de modèles parallèles \(PPL\).  Un objet `task` représente le travail qui peut être exécuté de façon asynchrone, et simultanément avec d'autres tâches et un travail parallèle généré par des algorithmes parallèles dans le runtime d'accès concurrentiel.  Il produit un résultat de type `_ResultType` une fois l'opération terminée correctement.  Les tâches du type `task<void>` ne produisent aucun résultat.  Une tâche peut être mise en attente et annulée indépendamment des autres tâches.  Elle peut également être composée d'autres tâches à l'aide des continuations \(`then`\) ainsi que de modèles de jointure \(`when_all`\) et de choix \(`when_any`\).  
  
## Syntaxe  
  
```  
template <  
   typename _Type  
>  
class task;  
  
template <>  
class task<void>;  
  
template<  
   typename _ReturnType  
>  
class task;  
```  
  
#### Paramètres  
 `_Type`  
 `T`  
 `_ReturnType`  
 Type de résultat de la tâche.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`result_type`|Type du résultat produit par un objet de cette classe.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task::task, constructeur](../Topic/task::task%20Constructor.md)|Surchargé.  Construit un objet `task`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[task::get, méthode](../Topic/task::get%20Method.md)|Surchargé.  Retourne le résultat auquel cette tâche s'est produit.  Si la tâche n'est pas dans un état terminal, un appel à `get` attend que la tâche se termine.  Cette méthode ne retourne pas de valeur lorsqu'elle est appelée sur une tâche dont le `result_type` a la valeur `void`.|  
|[task::is\_apartment\_aware, méthode](../Topic/task::is_apartment_aware%20Method.md)|Détermine si la tâche déroule une interface `IAsyncInfo` Windows Runtime ou est descendue de cette tâche.|  
|[task::is\_done, méthode \(runtime d'accès concurrentiel\)](../Topic/task::is_done%20Method%20\(Concurrency%20Runtime\).md)|Détermine si la tâche est terminée.|  
|[task::scheduler, méthode \(runtime d'accès concurrentiel\)](../Topic/task::scheduler%20Method%20\(Concurrency%20Runtime\).md)|Retourne le planificateur pour cette tâche|  
|[task::then, méthode](../Topic/task::then%20Method.md)|Surchargé.  Ajoute une tâche de continuation à cette tâche.|  
|[task::wait, méthode](../Topic/task::wait%20Method.md)|Attend que cette tâche atteigne un état terminal.  Il est possible que `wait` exécute la tâche inline, si toutes les dépendances de tâches sont remplies, et elle n'a pas déjà été prise pour l'exécution par un travail en arrière\-plan.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task::operator\!\=, opérateur](../Topic/task::operator!=%20Operator.md)|Surchargé.  Détermine si deux objets `task` représentent différentes tâches internes.|  
|[task::operator\=, opérateur](../Topic/task::operator=%20Operator.md)|Surchargé.  Remplace le contenu d'un objet `task` par un autre.|  
|[task::operator\=\=, opérateur](../Topic/task::operator==%20Operator.md)|Surchargé.  Détermine si deux objets `task` représentent la même tâche interne.|  
  
## Notes  
 Pour plus d'informations, consultez [Parallélisme des tâches](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Hiérarchie d'héritage  
 `task`  
  
## Configuration requise  
 **En\-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)