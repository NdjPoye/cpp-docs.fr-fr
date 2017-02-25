---
title: "concurrent_priority_queue, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_priority_queue/concurrency::concurrent_priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_priority_queue (classe)"
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# concurrent_priority_queue, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `concurrent_priority_queue` est un conteneur qui permet à plusieurs threads de pousser et dépiler simultanément des éléments.  Les éléments sont dépilés par ordre de priorité, où la priorité est déterminée par un foncteur fourni comme argument du modèle.  
  
## Syntaxe  
  
```  
template <  
   typename _Ty,  
   typename _Compare=std::less<_Ty>,  
   typename _Ax = std::allocator<_Ty>  
>  
, typename _Ax = std::allocator<_Ty> > class concurrent_priority_queue;  
```  
  
#### Paramètres  
 `_Ty`  
 Type de données des éléments à stocker dans la file d'attente prioritaire.  
  
 `_Compare`  
 Le type de l'objet de fonction qui peut comparer deux valeurs d'éléments comme clés de tri pour déterminer leur ordre relatif dans la file d'attente prioritaire.  Cet argument est facultatif et le prédicat binaire `less<``_Ty``>` est la valeur par défaut.  
  
 `_Ax`  
 Le type qui représente l'objet d'allocation stocké qui contient des détails sur l'allocation et la désallocation de mémoire pour la file d'attente prioritaire simultanée.  Cet argument est facultatif et la valeur par défaut est `allocator<``_Ty``>`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`allocator_type`|Type qui représente la classe d'allocateur pour la file d'attente simultanée prioritaire.|  
|`const_reference`|Un type qui représente une référence const à un élément du type stockées dans une file d'attente prioritaire simultanée.|  
|`reference`|Un type qui représente une référence à un élément du type stockées dans une file d'attente prioritaire simultanée.|  
|`size_type`|Type qui compte le nombre d'éléments dans une file d'attente simultanée prioritaire.|  
|`value_type`|Type qui représente le type de données stocké dans une file d'attente simultanée prioritaire.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_priority\_queue::concurrent\_priority\_queue, constructeur](../Topic/concurrent_priority_queue::concurrent_priority_queue%20Constructor.md)|Surchargé.  Construit une file d'attente simultanée prioritaire.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_priority\_queue::clear, méthode](../Topic/concurrent_priority_queue::clear%20Method.md)|Efface tous les éléments dans la priorité simultanée.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_priority\_queue::empty, méthode](../Topic/concurrent_priority_queue::empty%20Method.md)|Teste si la file d'attente simultanée prioritaire est vide à l'instant de l'appel de la méthode.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_priority\_queue::get\_allocator, méthode](../Topic/concurrent_priority_queue::get_allocator%20Method.md)|Retourne une copie de l'allocateur utilisé pour construire la file d'attente simultanée prioritaire.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_priority\_queue::push, méthode](../Topic/concurrent_priority_queue::push%20Method.md)|Surchargé.  Ajoute un élément à la file d'attente simultanée prioritaire.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_priority\_queue::size, méthode](../Topic/concurrent_priority_queue::size%20Method.md)|Retourne le nombre d'éléments contenus dans la file d'attente simultanée prioritaire.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_priority\_queue::swap, méthode](../Topic/concurrent_priority_queue::swap%20Method.md)|Habite le contenu de deux files d'attente à priorité déterminée simultanées.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_priority\_queue::try\_pop, méthode](../Topic/concurrent_priority_queue::try_pop%20Method.md)|Supprime et retourne l'élément à la priorité la plus élevée de la file d'attente si la file d'attente est vide.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_priority\_queue::operator\=, opérateur](../Topic/concurrent_priority_queue::operator=%20Operator.md)|Surchargé.  Assigne le contenu d'un autre objet `concurrent_priority_queue` à celui\-ci.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
  
## Notes  
 Pour plus d'informations sur la classe `concurrent_priority_queue`, consultez [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Hiérarchie d'héritage  
 `concurrent_priority_queue`  
  
## Configuration requise  
 **En\-tête :** concurrent\_priority\_queue.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md)