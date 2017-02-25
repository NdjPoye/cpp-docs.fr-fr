---
title: "tile_barrier, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tile_barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tile_barrier (classe)"
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# tile_barrier, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Synchronise l'exécution des threads qui s'exécutent dans le groupe de threads \(la mosaïque\) à l'aide des méthodes `wait`.  Seul le runtime peut instancier cette classe.  
  
## Syntaxe  
  
```  
class tile_barrier;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[tile\_barrier::tile\_barrier, constructeur](../Topic/tile_barrier::tile_barrier%20Constructor.md)|Initialise une nouvelle instance de la classe `tile_barrier`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tile\_barrier::wait, méthode](../Topic/tile_barrier::wait%20Method.md)|Demande à tous les threads de groupe de threads \(mosaïque\) d'arrêter l'exécution jusqu'à ce que tous les threads de la mosaïque aient terminé l'attente.|  
|[tile\_barrier::wait\_with\_all\_memory\_fence, méthode](../Topic/tile_barrier::wait_with_all_memory_fence%20Method.md)|Bloque l'exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire aient été effectués et que tous les threads de la mosaïque aient atteint cet appel.|  
|[tile\_barrier::wait\_with\_global\_memory\_fence, méthode](../Topic/tile_barrier::wait_with_global_memory_fence%20Method.md)|Bloque l'exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire globaux aient été effectués et que tous les threads de la mosaïque aient atteint cet appel.|  
|[tile\_barrier::wait\_with\_tile\_static\_memory\_fence, méthode](../Topic/tile_barrier::wait_with_tile_static_memory_fence%20Method.md)|Bloque l'exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire `tile_static` aient été effectués et que tous les threads de la mosaïque aient atteint cet appel.|  
  
## Hiérarchie d'héritage  
 `tile_barrier`  
  
## Configuration requise  
 **En\-tête :** amp.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)