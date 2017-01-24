---
title: "IResourceManager, structure | Microsoft Docs"
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
  - "concrtrm/concurrency::IResourceManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IResourceManager (structure)"
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IResourceManager, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Interface au Gestionnaire de ressources du runtime d'accès concurrentiel.  C'est l'interface par laquelle les planificateurs communiquent avec le Gestionnaire des ressources.  
  
## Syntaxe  
  
```  
struct IResourceManager;  
```  
  
## Membres  
  
### Énumérations publique  
  
|Nom|Description|  
|---------|-----------------|  
|[IResourceManager::OSVersion, énumération](../Topic/IResourceManager::OSVersion%20Enumeration.md)|Type énuméré qui représente la version du système d'exploitation.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IResourceManager::CreateNodeTopology, méthode](../Topic/IResourceManager::CreateNodeTopology%20Method.md)|Présente uniquement dans les versions de débogage du runtime, cette méthode est un crochet de test conçu pour faciliter le test du Gestionnaire de ressources sur divers topologies de matériel, sans que le matériel ne doive correspondre à la configuration.  Avec les versions commerciales du runtime, cette méthode sera retournée sans exécuter d'action.|  
|[IResourceManager::GetAvailableNodeCount, méthode](../Topic/IResourceManager::GetAvailableNodeCount%20Method.md)|Retourne le nombre de nœuds disponibles au gestionnaire de ressources.|  
|[IResourceManager::GetFirstNode, méthode](../Topic/IResourceManager::GetFirstNode%20Method.md)|Retourne le premier nœud dans l'ordre d'énumération comme défini par le gestionnaire de ressources.|  
|[IResourceManager::Reference, méthode](../Topic/IResourceManager::Reference%20Method.md)|Incrémente le nombre de références sur l'instance de Gestionnaire de ressources.|  
|[IResourceManager::RegisterScheduler, méthode](../Topic/IResourceManager::RegisterScheduler%20Method.md)|Inscrit un planificateur auprès du Gestionnaire de ressources.  Une fois le planificateur inscrit, il doit communiquer avec le Gestionnaire de ressources à l'aide de l'interface `ISchedulerProxy` retournée.|  
|[IResourceManager::Release, méthode](../Topic/IResourceManager::Release%20Method.md)|Décrémente le décompte de références sur l'instance de Gestionnaire des ressources.  Le Gestionnaire des ressources est détruit lorsque son décompte de références atteint `0`.|  
  
## Notes  
 Utilisez la fonction [CreateResourceManager](../Topic/CreateResourceManager%20Function.md) pour obtenir une interface pour l'instance du Gestionnaire des ressources du singleton.  La méthode incrémente un décompte de références sur le Gestionnaire des ressources, et vous devez appeler la méthode [IResourceManager::Release](../Topic/IResourceManager::Release%20Method.md) pour diffuser la référence lorsque vous avez fini avec le Gestionnaire des ressources.  En général, chaque planificateur que vous créez appellera cette méthode pendant la création, et diffusera la référence au Gestionnaire des ressources après sa fermeture.  
  
## Hiérarchie d'héritage  
 `IResourceManager`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISchedulerProxy, structure](../../../parallel/concrt/reference/ischedulerproxy-structure.md)   
 [IScheduler, structure](../../../parallel/concrt/reference/ischeduler-structure.md)