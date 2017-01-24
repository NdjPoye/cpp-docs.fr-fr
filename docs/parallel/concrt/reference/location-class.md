---
title: "location, classe | Microsoft Docs"
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
  - "concrt/concurrency::location"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "location (classe)"
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# location, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Une abstraction d'un emplacement physique sur le matériel hardware.  
  
## Syntaxe  
  
```  
class location;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[location::location, constructeur](../Topic/location::location%20Constructor.md)|Surchargé.  Construit un objet `location`.|  
|[location::~location, destructeur](../Topic/location::~location%20Destructor.md)|Détruit un objet `location`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[location::current, méthode](../Topic/location::current%20Method.md)|Retourne un objet `location` représentant l'emplacement le plus spécifique que le thread appelant exécute.|  
|[location::from\_numa\_node, méthode](../Topic/location::from_numa_node%20Method.md)|Retourne un objet `location` qui représente un nœud NUMA donné.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[location::operator\!\=, opérateur](../Topic/location::operator!=%20Operator.md)|Détermine si deux objets `location` représentent différents emplacements.|  
|[location::operator\=, opérateur](../Topic/location::operator=%20Operator.md)|Assigne le contenu d'un objet différent `location` à celui\-ci.|  
|[location::operator\=\=, opérateur](../Topic/location::operator==%20Operator.md)|Détermine si deux objets `location` représentent la même localisation.|  
  
## Hiérarchie d'héritage  
 `location`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)