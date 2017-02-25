---
title: "ITopologyNode, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ITopologyNode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyNode (structure)"
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ITopologyNode, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Une interface avec un nœud de topologie comme défini par le gestionnaire de ressources.  Un nœud contient une ou plusieurs ressources d'exécution.  
  
## Syntaxe  
  
```  
struct ITopologyNode;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ITopologyNode::GetExecutionResourceCount, méthode](../Topic/ITopologyNode::GetExecutionResourceCount%20Method.md)|Retourne le nombre de ressources d'exécution regroupées sous ce nœud.|  
|[ITopologyNode::GetFirstExecutionResource, méthode](../Topic/ITopologyNode::GetFirstExecutionResource%20Method.md)|Retourne la première ressource d'exécution regroupée sous ce nœud dans l'ordre d'énumération.|  
|[ITopologyNode::GetId, méthode](../Topic/ITopologyNode::GetId%20Method.md)|Retourne l'identificateur unique du gestionnaire de ressources pour ce nœud.|  
|[ITopologyNode::GetNext, méthode](../Topic/ITopologyNode::GetNext%20Method.md)|Retourne une interface au nœud de topologie suivant dans l'ordre d'énumération.|  
|[ITopologyNode::GetNumaNode, méthode](../Topic/ITopologyNode::GetNumaNode%20Method.md)|Retourne le nombre de nœud NUMA assigné par Windows auquel ce nœud de ressource Manager appartient.|  
  
## Notes  
 Cette interface est généralement utilisée pour parcourir la topologie du système comme observé par le gestionnaire de ressources.  
  
## Hiérarchie d'héritage  
 `ITopologyNode`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)