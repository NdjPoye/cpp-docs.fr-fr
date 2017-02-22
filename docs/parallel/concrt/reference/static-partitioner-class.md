---
title: "static_partitioner, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::static_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "static_partitioner (classe)"
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# static_partitioner, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe d' `static_partitioner` représente un partitionnement statique de la plage itérée au sein de par `parallel_for`.  Le partitionneur divise la plage dans autant de segments comme il existe des ouvriers disponibles au planificateur underyling.  
  
## Syntaxe  
  
```  
class static_partitioner;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[static\_partitioner::static\_partitioner, constructeur](../Topic/static_partitioner::static_partitioner%20Constructor.md)|Construit un objet `static_partitioner`.|  
|[static\_partitioner::~static\_partitioner, destructeur](../Topic/static_partitioner::~static_partitioner%20Destructor.md)|Détruit un objet `static_partitioner`.|  
  
## Hiérarchie d'héritage  
 `static_partitioner`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)