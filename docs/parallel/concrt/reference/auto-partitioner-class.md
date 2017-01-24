---
title: "auto_partitioner, classe | Microsoft Docs"
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
  - "ppl/concurrency::auto_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_partitioner (classe)"
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_partitioner, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe d' `auto_partitioner` représente la méthode par défaut `parallel_for`, `parallel_for_each` et utilisation d' `parallel_transform` de partitionner la plage qu'ils itère sur.  Cette méthode de la plage d'employes de partitionnement volant pour équilibrer la charge de ainsi que par\-itèrent l'annulation.  
  
## Syntaxe  
  
```  
class auto_partitioner;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[auto\_partitioner::auto\_partitioner, constructeur](../Topic/auto_partitioner::auto_partitioner%20Constructor.md)|Construit un objet `auto_partitioner`.|  
|[auto\_partitioner::~auto\_partitioner, destructeur](../Topic/auto_partitioner::~auto_partitioner%20Destructor.md)|Détruit un objet `auto_partitioner`.|  
  
## Hiérarchie d'héritage  
 `auto_partitioner`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)