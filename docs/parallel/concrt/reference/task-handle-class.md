---
title: "task_handle, classe | Microsoft Docs"
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
  - "ppl/concurrency::task_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_handle (classe)"
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_handle, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `task_handle` représente un élément de travail parallèle individuel.  Il encapsule les instructions et les données obligatoires pour exécuter un travail.  
  
## Syntaxe  
  
```  
template<  
   typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### Paramètres  
 `_Function`  
 Type de l'objet de fonction qui sera appelé pour exécuter le travail représenté par l'objet `task_handle`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_handle::task\_handle, constructeur](../Topic/task_handle::task_handle%20Constructor.md)|Construit un nouvel objet `task_handle`.  Le travail de la tâche est réalisé en appelant la fonction spécifiée comme un paramètre au constructeur.|  
|[task\_handle::~task\_handle, destructeur](../Topic/task_handle::~task_handle%20Destructor.md)|Détruit l'objet `task_handle`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[task\_handle::operator\(\), opérateur](../Topic/task_handle::operator\(\)%20Operator.md)|Opérateur d'appel de fonction appelé par le runtime pour exécuter le travail du handle de tâche.|  
  
## Notes  
 Les objets `task_handle` peuvent être utilisés conjointement à un `structured_task_group` ou un objet `task_group` plus général, pour décomposer le travail en tâches parallèles.  Pour plus d'informations, consultez [Parallélisme des tâches](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Notez que le créateur d'un objet `task_handle` est chargé de la maintenance de la durée de vie de l'objet `task_handle` créé, jusqu'à ce qu'il ne soit plus requis par le runtime d'accès concurrentiel.  En général, cela signifie que l'objet `task_handle` ne doit détruire jusqu'à ce que la méthode `wait` ou `run_and_wait` du `task_group` ou `structured_task_group` dans lequel il est mis en file d'attente ait été appelée.  
  
 Les objets `task_handle` sont utilisés en général conjointement à des expressions lambda C\+\+.  Étant donné que vous ne connaissez pas le type réel de lambda, la fonction [make\_task](../Topic/make_task%20Function.md) est généralement utilisée pour créer un objet `task_handle`.  
  
 Le runtime créé une copie de la fonction de travail que vous passez sur un objet `task_handle`.  Par conséquent, aucune modification d'état se produisant dans un objet de fonction que vous passez à un objet `task_handle` ne s'affichera dans votre copie de cet objet de fonction.  
  
## Hiérarchie d'héritage  
 `task_handle`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group, classe](../Topic/task_group%20Class.md)   
 [structured\_task\_group, classe](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [make\_task, fonction](../Topic/make_task%20Function.md)   
 [task\_group::run, méthode](../Topic/task_group::run%20Method.md)   
 [task\_group::wait, méthode](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait, méthode](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group::run, méthode](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait, méthode](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait, méthode](../Topic/structured_task_group::run_and_wait%20Method.md)