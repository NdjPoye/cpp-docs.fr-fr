---
title: "structured_task_group, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::structured_task_group"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "structured_task_group (classe)"
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# structured_task_group, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `structured_task_group` représente une collection très structurée de travail parallèle.  Vous pouvez mettre en file d'attente des tâches parallèles individuelles dans un `structured_task_group` à l'aide d'objets `task_handle` et attendre qu'elles se terminent, ou annuler le groupe de tâches avant la fin de leur exécution, ce qui conduira à l'abandon de toutes les tâches qui n'ont pas commencé.  
  
## Syntaxe  
  
```  
class structured_task_group;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[structured\_task\_group::structured\_task\_group, constructeur](../Topic/structured_task_group::structured_task_group%20Constructor.md)|Surchargé.  Construit un nouvel objet `structured_task_group`.|  
|[structured\_task\_group::~structured\_task\_group, destructeur](../Topic/structured_task_group::~structured_task_group%20Destructor.md)|Détruit un objet `structured_task_group`.  Vous devez appeler la méthode `wait` ou `run_and_wait` sur l'objet avant exécution du destructeur, sauf si le destructeur s'exécute suite au déroulement de pile en raison d'une exception.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[structured\_task\_group::cancel, méthode](../Topic/structured_task_group::cancel%20Method.md)|Fait son possible pour annuler la sous\-arborescence de travail rattachée à ce groupe de tâches.  Chaque tâche planifiée sur le groupe de tâches sera annulée de manière transitive si possible.|  
|[structured\_task\_group::is\_canceling, méthode](../Topic/structured_task_group::is_canceling%20Method.md)|Indique à l'appelant si le groupe de tâches est actuellement en cours d'annulation ou pas.  Cela n'indique pas nécessairement que la méthode `cancel` a été appelée sur l'objet `structured_task_group` \(bien que dans ce cas la méthode retourne la valeur `true`\).  Cela peut être dû au fait que l'objet `structured_task_group` s'exécute inline et qu'un groupe de tâches supplémentaire en haut de l'arborescence travail a été annulé.  Dans de tels cas où l'exécution peut déterminer à l'avance que cette annulation passera via cet objet `structured_task_group`, `true` sera également retourné.|  
|[structured\_task\_group::run, méthode](../Topic/structured_task_group::run%20Method.md)|Surchargé.  Planifie une tâche sur l'objet `structured_task_group`.  L'appelant gère la durée de vie de l'objet `task_handle` passé dans le paramètre `_Task_handle`.  La version qui accepte le paramètre `_Placement` implique que la tâche soit influencé par rapport à l'execution à l'emplacement spécifié par le paramètre.|  
|[structured\_task\_group::run\_and\_wait, méthode](../Topic/structured_task_group::run_and_wait%20Method.md)|Surchargé.  Planifie une tâche devant s'exécuter inline dans le contexte d'appel avec l'assistance de l'objet `structured_task_group` pour une prise en charge complète de l'annulation.  Si un objet `task_handle` est passé comme paramètre à `run_and_wait`, l'appelant est responsable de la gestion de la durée de vie de l'objet `task_handle`.  La fonction attend ensuite que tout le travail sur l'objet `structured_task_group` soit terminé ou ait été annulé.|  
|[structured\_task\_group::wait, méthode](../Topic/structured_task_group::wait%20Method.md)|Attend que tout le travail sur `structured_task_group` soit terminé ou ait été annulé.|  
  
## Notes  
 Il existe plusieurs restrictions importantes à l'utilisation d'un objet `structured_task_group` pour améliorer la performance :  
  
-   Un objet `structured_task_group` unique ne peut pas être utilisé par plusieurs threads.  Toutes les opérations sur un objet `structured_task_group` doivent être exécutées par le thread qui a créé l'objet.  Les deux exceptions à cette règle sont les fonctions membres `cancel` et `is_canceling`.  L'objet ne peut pas être dans la liste de capture d'une expression lambda et être utilisé dans une tâche, à moins que la tâche utilise l'une des opérations d'annulation.  
  
-   Toutes les tâches planifiées pour un objet `structured_task_group` sont planifiées via l'utilisation d'objets `task_handle` dont vous devez gérer explicitement la durée de vie.  
  
-   Plusieurs groupes peuvent uniquement être utilisés dans un ordre absolument imbriqué.  Si deux objets `structured_task_group` sont déclarés, le deuxième à être déclaré \(l'objet interne\) doit être détruit avant toute autre méthode sauf `cancel` ou `is_canceling` est appelé sur le premier objet \(externe\).  Cette condition est vraie en cas de simple déclaration de plusieurs objets `structured_task_group` dans des portées identiques ou fonctionnellement imbriquées et si une tâche a été mise en file d'attente dans `structured_task_group` via la méthode `run` ou `run_and_wait`.  
  
-   Contrairement à la classe `task_group` générale, tous les états dans la classe `structured_task_group` sont finaux.  Après que vous ayez mis en file d'attente des tâches du groupe et ayez attendu qu'elles se terminent, vous ne pouvez plus utiliser le même groupe.  
  
 Pour plus d'informations, consultez [Parallélisme des tâches](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Hiérarchie d'héritage  
 `structured_task_group`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group, classe](../Topic/task_group%20Class.md)   
 [task\_handle, classe](../../../parallel/concrt/reference/task-handle-class.md)