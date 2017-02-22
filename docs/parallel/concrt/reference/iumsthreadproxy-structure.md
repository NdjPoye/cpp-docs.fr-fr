---
title: "IUMSThreadProxy, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSThreadProxy (structure)"
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# IUMSThreadProxy, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Abstraction d'un thread d'exécution.  Si vous souhaitez que des threads planifiables en mode utilisateur \(UMS\) soient accordés à votre planificateur, définissez la valeur de l'élément de stratégie du planificateur `SchedulerKind` sur `UmsThreadDefault` et implémentez l'interface `IUMSScheduler`.  Les threads UMS sont pris en charge uniquement sur les systèmes d'exploitation 64 bits avec la version Windows 7 et supérieure.  
  
## Syntaxe  
  
```  
struct IUMSThreadProxy : public IThreadProxy;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IUMSThreadProxy::EnterCriticalRegion, méthode](../Topic/IUMSThreadProxy::EnterCriticalRegion%20Method.md)|Appelé pour accéder à une région critique.  Dans une région critique, le planificateur n'observera pas les opérations bloquantes asynchrones qui se produisent.  Cela signifie que le planificateur ne sera pas réentré pour les erreurs de page, les arrêts de thread, les appels de procédure asynchrone de noyau \(APC\), et ainsi de suite, pour un thread UMS.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion, méthode](../Topic/IUMSThreadProxy::EnterHyperCriticalRegion%20Method.md)|Appelé pour accéder à une région hyper\-critique.  Dans une région hyper\-critique, le planificateur n'observera aucun des opérations bloquantes qui se produisent.  Cela signifie que le planificateur ne sera pas réentré pour les appels de fonction bloquants, les tentatives d'acquisition du verrou qui se bloquent, les erreurs de page, les arrêts de thread, les appels de procédure asynchrone de noyau \(APC\), et ainsi de suite, pour un thread UMS.|  
|[IUMSThreadProxy::ExitCriticalRegion, méthode](../Topic/IUMSThreadProxy::ExitCriticalRegion%20Method.md)|Appelé pour quitter une région critique.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion, méthode](../Topic/IUMSThreadProxy::ExitHyperCriticalRegion%20Method.md)|Appelé pour quitter une région hyper\-critique.|  
|[IUMSThreadProxy::GetCriticalRegionType, méthode](../Topic/IUMSThreadProxy::GetCriticalRegionType%20Method.md)|Retourne dans quel type de région critique se trouve le proxy de thread.  Etant donné que les régions hyper\-critiques sont un sur\-ensemble de régions critiques, si le code a pénétré une région critique, puis une région hyper\-critique, `InsideHyperCriticalRegion` sera retourné.|  
  
## Hiérarchie d'héritage  
 [IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler, structure](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [SchedulerType, énumération](../Topic/SchedulerType%20Enumeration.md)