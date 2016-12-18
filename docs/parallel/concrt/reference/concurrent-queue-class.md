---
title: "concurrent_queue, classe | Microsoft Docs"
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
  - "concurrent_queue/concurrency::concurrent_queue"
  - "concurrent_queue/Concurrency::concurrent_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_queue (classe)"
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_queue, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `concurrent_queue` est une classe de conteneur de séquences qui autorise l'accès premier entré, premier sorti à ses éléments.  Il active un jeu limité d'opérations d'accès concurrentiel, telles que `push` et `try_pop`.  
  
## Syntaxe  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;  
```  
  
#### Paramètres  
 `_Ty`  
 Type de données des éléments à stocker dans la file d'attente.  
  
 `_Ax`  
 Type qui représente l'objet d'allocation stocké qui contient des détails sur l'allocation et la désallocation de mémoire pour cette file d'attente simultanée.  Cet argument est facultatif et la valeur par défaut est `allocator<``_Ty``>`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`allocator_type`|Type qui représente la classe d'allocateur pour la file d'attente simultanée.|  
|`const_iterator`|Type qui représente un itérateur `const` non thread\-safe sur les éléments dans une file d'attente simultanée.|  
|`const_reference`|Type qui fournit une référence à un élément `const` stocké dans une file d'attente simultanée pour la lecture et l'exécution d'opérations `const`.|  
|`difference_type`|Type qui fournit la distance signée entre deux éléments dans une file d'attente simultanée.|  
|`iterator`|Type qui représente un itérateur non thread\-safe sur les éléments dans une file d'attente simultanée.|  
|`reference`|Type qui fournit une référence à un élément stocké dans une file d'attente simultanée.|  
|`size_type`|Type qui compte le nombre d'éléments dans une file d'attente simultanée.|  
|`value_type`|Type qui représente le type de données stocké dans une file d'attente simultanée.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_queue::concurrent\_queue, constructeur](../Topic/concurrent_queue::concurrent_queue%20Constructor.md)|Surchargé.  Construit une file d'attente simultanée.|  
|[concurrent\_queue::~concurrent\_queue, destructeur](../Topic/concurrent_queue::~concurrent_queue%20Destructor.md)|Détruit la file d'attente simultanée.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_queue::clear, méthode](../Topic/concurrent_queue::clear%20Method.md)|Efface la file d'attente simultanée, en détruisant les éléments actuellement dans la file.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::empty, méthode](../Topic/concurrent_queue::empty%20Method.md)|Teste si la file d'attente simultanée est vide au moment de l'appel de la méthode.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::get\_allocator, méthode](../Topic/concurrent_queue::get_allocator%20Method.md)|Retourne une copie de l'allocateur utilisé pour construire la file d'attente simultanée.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::push, méthode](../Topic/concurrent_queue::push%20Method.md)|Surchargé.  Place un élément à la fin de la file d'attente simultanée.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::try\_pop, méthode](../Topic/concurrent_queue::try_pop%20Method.md)|Enlève un élément de la file d'attente s'il y en a un de disponible.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::unsafe\_begin, méthode](../Topic/concurrent_queue::unsafe_begin%20Method.md)|Surchargé.  Retourne un itérateur de type `iterator` ou `const_iterator` au début de la file d'attente simultanée.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::unsafe\_end, méthode](../Topic/concurrent_queue::unsafe_end%20Method.md)|Surchargé.  Retourne un itérateur de type `iterator` ou `const_iterator` à la fin de la file d'attente simultanée.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_queue::unsafe\_size, méthode](../Topic/concurrent_queue::unsafe_size%20Method.md)|Retourne le nombre d'éléments de la file d'attente.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
  
## Notes  
 Pour plus d'informations, consultez [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Hiérarchie d'héritage  
 `concurrent_queue`  
  
## Configuration requise  
 **En\-tête :** concurrent\_queue.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)