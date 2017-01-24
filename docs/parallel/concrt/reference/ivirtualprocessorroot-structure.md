---
title: "IVirtualProcessorRoot, structure | Microsoft Docs"
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
  - "concrtrm/concurrency::IVirtualProcessorRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IVirtualProcessorRoot (structure)"
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IVirtualProcessorRoot, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Abstraction d'un thread matériel sur laquelle un proxy de thread peut s'exécuter.  
  
## Syntaxe  
  
```  
struct IVirtualProcessorRoot : public IExecutionResource;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IVirtualProcessorRoot::Activate, méthode](../Topic/IVirtualProcessorRoot::Activate%20Method.md)|Implique que le proxy de thread associé au `pContext` d'interface du contexte d'exécution démarre l'exécution sur cette racine de processeur virtuel.|  
|[IVirtualProcessorRoot::Deactivate, méthode](../Topic/IVirtualProcessorRoot::Deactivate%20Method.md)|Implique que le proxy de thread qui s'exécute actuellement sur cette racine de processeur virtuel arrête de distribuer le contexte d'exécution.  Le proxy de thread reprendra l'exécution au moment de l'appel à la méthode `Activate`.|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible, méthode](../Topic/IVirtualProcessorRoot::EnsureAllTasksVisible%20Method.md)|A pour effet de rendre visibles à tous les processeurs sur le système les données stockées dans la hiérarchie de la mémoire de processeurs individuels.  Il vérifie qu'une barrière de mémoire a été exécuté sur tous les processeurs avant que la méthode ne soit retournée.|  
|[IVirtualProcessorRoot::GetId, méthode](../Topic/IVirtualProcessorRoot::GetId%20Method.md)|Retourne un identificateur unique pour la racine de processeur virtuel.|  
  
## Notes  
 Chaque racine de processeur virtuel a une ressource d'exécution associée.  L'interface hérite de la classe `IVirtualProcessorRoot` à partir de l'interface [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md).  Plusieurs racines de processeur virtuel peuvent correspondre au même thread matériel sous\-jacent.  
  
 Le Gestionnaire des ressources accorde des racines de processeur virtuel aux planificateurs en réponse aux demandes de ressources.  Un planificateur peut utiliser une racine de processeur virtuel pour exécuter un travail en l'activant avec un contexte d'exécution.  
  
## Hiérarchie d'héritage  
 [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)