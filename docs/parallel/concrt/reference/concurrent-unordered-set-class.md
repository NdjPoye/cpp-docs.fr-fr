---
title: "concurrent_unordered_set, classe | Microsoft Docs"
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
  - "concurrent_unordered_set/concurrency::concurrent_unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_set (classe)"
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_set, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `concurrent_unordered_set` est un conteneur sécurisé du point de vue de l'accès concurrentiel qui contrôle une séquence de longueur variable d'éléments de type \_Key\_type.  La séquence est représentée de manière à autoriser les opérations d'ajout, d'accès aux éléments, d'accès aux itérateurs et de parcours d'itérateur sécurisées du point de vue de l'accès concurrentiel.  
  
## Syntaxe  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_set : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
```  
  
#### Paramètres  
 `_Key_type`  
 Type de clé.  
  
 `_Hasher`  
 Type d'objet de la fonction de hachage.  Cet argument est facultatif et la valeur par défaut est `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Type d'objet de fonction de comparaison d'égalité.  Cet argument est facultatif et la valeur par défaut est `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Type qui représente l'objet d'allocation stocké qui contient des détails sur l'allocation et la désallocation de mémoire pour la série non classée simultanée.  Cet argument est facultatif et la valeur par défaut est `std::allocator<``_Key_type``>`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`allocator_type`|Type d'un allocateur pour la gestion du stockage.|  
|`const_iterator`|Type d'un itérateur constant pour la séquence contrôlée.|  
|`const_local_iterator`|Type d'un itérateur de compartiment constant pour la séquence contrôlée.|  
|`const_pointer`|Type d'un pointeur constant vers un élément.|  
|`const_reference`|Type d'une référence constante à un élément.|  
|`difference_type`|Type d'une distance signée entre deux éléments.|  
|`hasher`|Type de la fonction de hachage.|  
|`iterator`|Type d'un itérateur pour la séquence contrôlée.|  
|`key_equal`|Type de la fonction de comparaison.|  
|`key_type`|Type d'une clé de classement.|  
|`local_iterator`|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|`pointer`|Type d'un pointeur vers un élément.|  
|`reference`|Type d'une référence à un élément.|  
|`size_type`|Type d'une distance non signée entre deux éléments.|  
|`value_type`|Le type d'un élément.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_unordered\_set::concurrent\_unordered\_set, constructeur](../Topic/concurrent_unordered_set::concurrent_unordered_set%20Constructor.md)|Surchargé.  Construit une série non classée simultanée.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_unordered\_set::hash\_function, méthode](../Topic/concurrent_unordered_set::hash_function%20Method.md)|Retourne l'objet de fonction de hachage stocké.|  
|[concurrent\_unordered\_set::insert, méthode](../Topic/concurrent_unordered_set::insert%20Method.md)|Surchargé.  Ajoute des éléments à l'objet `concurrent_unordered_set`.|  
|[concurrent\_unordered\_set::key\_eq, méthode](../Topic/concurrent_unordered_set::key_eq%20Method.md)|Retourne l'objet de fonction de comparaison d'égalité stocké.|  
|[concurrent\_unordered\_set::swap, méthode](../Topic/concurrent_unordered_set::swap%20Method.md)|Échange le contenu de deux objets `concurrent_unordered_set`.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_unordered\_set::unsafe\_erase, méthode](../Topic/concurrent_unordered_set::unsafe_erase%20Method.md)|Surchargé.  Supprime les éléments de `concurrent_unordered_set` aux positions spécifiées.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_unordered\_set::operator\=, opérateur](../Topic/concurrent_unordered_set::operator=%20Operator.md)|Surchargé.  Assigne le contenu d'un autre objet `concurrent_unordered_set` à celui\-ci.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
  
## Notes  
 Pour plus d'informations sur la classe `concurrent_unordered_set`, consultez [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Hiérarchie d'héritage  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## Configuration requise  
 **En\-tête :** concurrent\_unordered\_set.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md)