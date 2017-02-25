---
title: "Classe concurrent_vector | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_vector/Concurrency::concurrent_vector"
  - "concurrent_vector/concurrency::concurrent_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_vector (classe)"
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Classe concurrent_vector
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `concurrent_vector` est une classe de conteneur de séquences qui autorise l'accès aléatoire à tout élément.  Il vérifie l'accès concurrentiel ajout, d'accès aux éléments, d'accès aux itérateurs, et opérations de parcours d'itérateur.  
  
## Syntaxe  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_vector: protected details::_Allocator_base<_Ty, _Ax>, private details::_Concurrent_vector_base_v4;  
```  
  
#### Paramètres  
 `_Ty`  
 Type de données des éléments à stocker dans le vecteur.  
  
 `_Ax`  
 Type qui représente l'objet d'allocation stocké qui contient des détails sur l'allocation et la désallocation de mémoire pour le vecteur simultané.  Cet argument est facultatif et la valeur par défaut est `allocator<``_Ty``>`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`allocator_type`|Type qui représente la classe d'allocateur pour le vecteur simultané.|  
|`const_iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire un élément `const` dans un vecteur simultané.|  
|`const_pointer`|Type qui fournit un pointeur vers un élément `const` dans un vecteur simultané.|  
|`const_reference`|Type qui fournit une référence à un élément `const` stocké dans un vecteur simultané pour la lecture et l'exécution d'opérations `const`.|  
|`const_reverse_iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire tout élément `const` dans le vecteur simultané.|  
|`difference_type`|Type qui fournit la distance signée entre deux éléments dans un vecteur simultané.|  
|`iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire tout élément dans un vecteur simultané.  La modification d'un élément à l'aide de l'itérateur n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|`pointer`|Type qui fournit un pointeur vers un élément dans un vecteur simultané.|  
|`reference`|Type qui fournit une référence à un élément stocké dans un vecteur simultané.|  
|`reverse_iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire tout élément dans un vecteur simultané inversé.  La modification d'un élément à l'aide de l'itérateur n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|`size_type`|Type qui compte le nombre d'éléments dans un vecteur simultané.|  
|`value_type`|Type qui représente le type de données stocké dans un vecteur simultané.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_vector::concurrent\_vector, constructeur](../Topic/concurrent_vector::concurrent_vector%20Constructor.md)|Surchargé.  Construit un vecteur simultané.|  
|[concurrent\_vector::~concurrent\_vector, destructeur](../Topic/concurrent_vector::~concurrent_vector%20Destructor.md)|Efface tous les éléments et détruit ce vecteur simultané.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_vector::assign, méthode](../Topic/concurrent_vector::assign%20Method.md)|Surchargé.  Efface les éléments du vecteur simultané et lui attribue `_N` copies de `_Item`, ou des valeurs spécifiées par la plage d'itérateurs \[`_Begin`, `_End`\).  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::at, méthode](../Topic/concurrent_vector::at%20Method.md)|Surchargé.  Fournit l'accès à l'élément à l'index donné dans le vecteur simultané.  Cette méthode est protégée contre l'accès concurrentiel pour les opérations de lecture de même que pendant l'augmentation du vecteur, à condition que vous ayez vérifié que la valeur `_Index` est inférieure à la taille du vecteur simultané.|  
|[concurrent\_vector::back, méthode](../Topic/concurrent_vector::back%20Method.md)|Surchargé.  Retourne une référence ou une référence `const` au dernier élément dans le vecteur simultané.  Si le vecteur simultané est vide, la valeur de retour n'est pas définie.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::begin, méthode](../Topic/concurrent_vector::begin%20Method.md)|Surchargé.  Retourne un itérateur de type `iterator` ou `const_iterator` au début du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::capacity, méthode](../Topic/concurrent_vector::capacity%20Method.md)|Retourne la taille maximale que le vecteur simultané peut atteindre sans devoir allouer plus de mémoire.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::cbegin, méthode](../Topic/concurrent_vector::cbegin%20Method.md)|Retourne un itérateur de type `const_iterator` au début du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::cend, méthode](../Topic/concurrent_vector::cend%20Method.md)|Retourne un itérateur de type `const_iterator` à la fin du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::clear, méthode](../Topic/concurrent_vector::clear%20Method.md)|Efface tous les éléments dans le vecteur simultané.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::crbegin, méthode](../Topic/concurrent_vector::crbegin%20Method.md)|Retourne un itérateur de type `const_reverse_iterator` au début du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::crend, méthode](../Topic/concurrent_vector::crend%20Method.md)|Retourne un itérateur de type `const_reverse_iterator` à la fin du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::empty, méthode](../Topic/concurrent_vector::empty%20Method.md)|Teste si le vecteur simultané est vide au moment de l'appel de la méthode.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::end, méthode](../Topic/concurrent_vector::end%20Method.md)|Surchargé.  Retourne un itérateur de type `iterator` ou `const_iterator` à la fin du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::front, méthode](../Topic/concurrent_vector::front%20Method.md)|Surchargé.  Retourne une référence ou une référence `const` au premier élément dans le vecteur simultané.  Si le vecteur simultané est vide, la valeur de retour n'est pas définie.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::get\_allocator, méthode](../Topic/concurrent_vector::get_allocator%20Method.md)|Retourne une copie de l'allocateur utilisé pour construire le vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::grow\_by, méthode](../Topic/concurrent_vector::grow_by%20Method.md)|Surchargé.  Augmente ce vecteur simultané par les éléments `_Delta`.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::grow\_to\_at\_least, méthode](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|Augmente ce vecteur simultané jusqu'à ce qu'il ait au moins `_N` éléments.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::max\_size, méthode](../Topic/concurrent_vector::max_size%20Method.md)|Retourne le nombre maximal d'éléments que le vecteur simultané peut contenir.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::push\_back, méthode](../Topic/concurrent_vector::push_back%20Method.md)|Surchargé.  Ajoute l'élément donné à la fin du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::rbegin, méthode](../Topic/concurrent_vector::rbegin%20Method.md)|Surchargé.  Retourne un itérateur de type `reverse_iterator` ou `const_reverse_iterator` au début du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::rend, méthode](../Topic/concurrent_vector::rend%20Method.md)|Surchargé.  Retourne un itérateur de type `reverse_iterator` ou `const_reverse_iterator` à la fin du vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::reserve, méthode](../Topic/concurrent_vector::reserve%20Method.md)|Alloue suffisamment d'espace pour augmenter le vecteur simultané jusqu'à la taille `_N` sans avoir à allouer plus de mémoire ultérieurement.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::resize, méthode](../Topic/concurrent_vector::resize%20Method.md)|Surchargé.  Modifie la taille du vecteur simultané en lui attribuant la taille demandée, en supprimant ou en ajoutant des éléments si nécessaire.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::shrink\_to\_fit, méthode](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|Condense la représentation interne du vecteur simultané pour réduire la fragmentation et optimiser l'utilisation de la mémoire.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::size, méthode](../Topic/concurrent_vector::size%20Method.md)|Retourne le nombre d'éléments dans le vecteur simultané.  Cette méthode est sécurisée du point de vue de l'accès concurrentiel.|  
|[concurrent\_vector::swap, méthode](../Topic/concurrent_vector::swap%20Method.md)|Échange le contenu de deux vecteurs simultanés.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[concurrent\_vector::operatorOperator](../Topic/concurrent_vector::operatorOperator.md)|Surchargé.  Fournit l'accès à l'élément à l'index donné dans le vecteur simultané.  Cette méthode est protégée contre l'accès concurrentiel pour les opérations de lecture de même que pendant l'augmentation du vecteur, à condition que vous ayez vérifié que la valeur `_Index` est inférieure à la taille du vecteur simultané.|  
|[concurrent\_vector::operator\=, opérateur](../Topic/concurrent_vector::operator=%20Operator.md)|Surchargé.  Assigne le contenu d'un autre objet `concurrent_vector` à celui\-ci.  Cette méthode n'est pas sécurisée du point de vue de l'accès concurrentiel.|  
  
## Notes  
 Pour plus d'informations sur la classe `concurrent_vector`, consultez [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Hiérarchie d'héritage  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## Configuration requise  
 **En\-tête :** concurrent\_vector.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md)