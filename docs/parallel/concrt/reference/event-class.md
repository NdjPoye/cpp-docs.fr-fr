---
title: "event, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event (classe)"
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# event, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Événement de réinitialisation manuelle qui est explicitement informé du runtime d'accès concurrentiel.  
  
## Syntaxe  
  
```  
class event;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[event::~event, destructeur](../Topic/event::~event%20Destructor.md)|Détruit un événement.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[event::reset, méthode](../Topic/event::reset%20Method.md)|Réinitialise l'événement à un état non signalé.|  
|[event::set, méthode](../Topic/event::set%20Method.md)|Signale l'événement .|  
|[event::wait, méthode](../Topic/event::wait%20Method.md)|Attend que l'événement soit signalé.|  
|[event::wait\_for\_multiple, méthode](../Topic/event::wait_for_multiple%20Method.md)|Attend que plusieurs événements soient signalés.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[event::timeout\_infinite, constante](../Topic/event::timeout_infinite%20Constant.md)|Valeur qui indique qu'une attente ne doit jamais expirer.|  
  
## Notes  
 Pour plus d'informations, consultez [Structures de données de synchronisation](../../../parallel/concrt/synchronization-data-structures.md).  
  
## Hiérarchie d'héritage  
 `event`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)