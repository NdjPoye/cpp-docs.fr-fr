---
title: "affinity_partitioner, classe | Microsoft Docs"
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
  - "ppl/concurrency::affinity_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "affinity_partitioner (classe)"
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# affinity_partitioner, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe d' `affinity_partitioner` est semblable à la classe d' `static_partitioner` , mais elle améliore l'affinité de cache par son choix de subranges de mappage aux threads de travail.  Elle peut améliorer les performances de manière significative lorsqu'une boucle est exécutée de nouveau sur le même groupe de données, et les ajustements de données dans le cache.  Notez que le même objet d' `affinity_partitioner` doit être utilisé avec les itérations suivantes d'une boucle parallèle qui est exécutée sur un groupe de données particulier, pour tirer parti de la localité des données.  
  
## Syntaxe  
  
```  
class affinity_partitioner;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[affinity\_partitioner::affinity\_partitioner, constructeur](../Topic/affinity_partitioner::affinity_partitioner%20Constructor.md)|Construit un objet `affinity_partitioner`.|  
|[affinity\_partitioner::~affinity\_partitioner, destructeur](../Topic/affinity_partitioner::~affinity_partitioner%20Destructor.md)|Détruit un objet `affinity_partitioner`.|  
  
## Hiérarchie d'héritage  
 `affinity_partitioner`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)