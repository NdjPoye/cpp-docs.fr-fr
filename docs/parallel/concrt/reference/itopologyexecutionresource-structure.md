---
title: "ITopologyExecutionResource, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ITopologyExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyExecutionResource (structure)"
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ITopologyExecutionResource, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Une interface avec une ressource d'exécution comme défini par le gestionnaire de ressources.  
  
## Syntaxe  
  
```  
struct ITopologyExecutionResource;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ITopologyExecutionResource::GetId, méthode](../Topic/ITopologyExecutionResource::GetId%20Method.md)|Retourne l'identificateur unique du gestionnaire de ressources pour cette ressource exécution.|  
|[ITopologyExecutionResource::GetNext, méthode](../Topic/ITopologyExecutionResource::GetNext%20Method.md)|Retourne une interface à la ressource suivante d'exécution de la commande d'énumération.|  
  
## Notes  
 Cette interface est généralement utilisée pour parcourir la topologie du système comme observé par le gestionnaire de ressources.  
  
## Hiérarchie d'héritage  
 `ITopologyExecutionResource`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)