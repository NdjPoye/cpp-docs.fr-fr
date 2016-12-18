---
title: "thread, classe | Microsoft Docs"
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
  - "thread/std::thread"
dev_langs: 
  - "C++"
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# thread, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit un objet utilisé afin d'observer et de gérer un thread d'exécution dans une application.  
  
## Syntaxe  
  
```  
class thread;  
```  
  
## Notes  
 Utilisez un objet `thread` afin d'observer et de gérer un thread d'exécution dans une application.  Un objet thread créé à l'aide du constructeur par défaut n'est associé à aucun thread d'exécution.  Un objet thread qui est construit à l'aide d'un objet appelable crée un thread d'exécution et appelle cet objet dans ce thread.  Les objets threads peuvent être déplacés mais pas copiés.  Par conséquent, un thread d'exécution peut être associé à un seul objet thread.  
  
 Chaque thread d'exécution a un identificateur unique de type `thread::id`.  La fonction `this_thread::get_id` retourne l'identificateur du thread appelant.  La fonction membre `thread::get_id` retourne l'identificateur du thread qui est géré par un objet thread.  Pour un objet thread construit par défaut, la méthode `thread::get_id` retourne un objet qui a une valeur qui est la même pour tous les objets thread construits par défaut et différente de la valeur retournée par `this_thread::get_id` pour tout thread d'exécution qui peut être joint au moment de l'appel.  
  
## Membres  
  
### Classes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[thread::id, classe](../Topic/thread::id%20Class.md)|Identifie de façon unique le thread associé.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[thread::thread, constructeur](../Topic/thread::thread%20Constructor.md)|Construit un objet `thread`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[thread::detach, méthode](../Topic/thread::detach%20Method.md)|Détache le thread associé de l'objet `thread`.|  
|[thread::get\_id, méthode](../Topic/thread::get_id%20Method.md)|Retourne l'identificateur unique du thread associé.|  
|[thread::hardware\_concurrency, méthode](../Topic/thread::hardware_concurrency%20Method.md)|Static.  Retourne une estimation du nombre de contextes de thread matériels.|  
|[thread::join, méthode](../Topic/thread::join%20Method.md)|Bloque jusqu'à ce que le thread associé se termine.|  
|[thread::joinable, méthode](../Topic/thread::joinable%20Method.md)|Spécifie si le thread associé est joignable.|  
|[thread::native\_handle, méthode](../Topic/thread::native_handle%20Method.md)|Retourne le type spécifique à l'implémentation qui représente le handle du thread.|  
|[thread::swap, méthode](../Topic/thread::swap%20Method.md)|Permute l'état de l'objet avec un objet `thread` spécifié.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[thread::operator\=, opérateur](../Topic/thread::operator=%20Operator.md)|Associe un thread à l'objet `thread` actuel.|  
  
## Configuration requise  
 **En\-tête :** thread  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread\>](../standard-library/thread.md)