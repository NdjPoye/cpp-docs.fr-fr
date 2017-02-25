---
title: "simple_partitioner, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::simple_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "simple_partitioner (classe)"
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# simple_partitioner, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe d' `simple_partitioner` représente un partitionnement statique de la plage itérée au sein de par `parallel_for`.  Le partitionneur divise la plage en segments de sorte que chaque segment possède au moins le nombre d'itérations spécifiées par la taille du segment.  
  
## Syntaxe  
  
```  
class simple_partitioner;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[simple\_partitioner::simple\_partitioner, constructeur](../Topic/simple_partitioner::simple_partitioner%20Constructor.md)|Construit un objet `simple_partitioner`.|  
|[simple\_partitioner::~simple\_partitioner, destructeur](../Topic/simple_partitioner::~simple_partitioner%20Destructor.md)|Détruit un objet `simple_partitioner`.|  
  
## Hiérarchie d'héritage  
 `simple_partitioner`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)