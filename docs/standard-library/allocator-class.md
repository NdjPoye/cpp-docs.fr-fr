---
title: "allocator, classe | Microsoft Docs"
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
  - "std::allocator"
  - "allocator"
  - "memory/std::allocator"
  - "std.allocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator (classe)"
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle décrit un objet qui gère l'allocation et la libération de stockage pour des tableaux d'objets de type **Type**. Un objet de classe **allocator** est l'objet allocateur par défaut spécifié dans les constructeurs pour plusieurs classes de modèles de conteneurs dans la bibliothèque C\+\+ standard.  
  
## Syntaxe  
  
```  
  
template <class   
Type  
>  
class allocator  
  
```  
  
#### Paramètres  
 *Type*  
 Type d'objet pour lequel le stockage est alloué ou libéré.  
  
## Notes  
 Tous les conteneurs STL ont un paramètre de modèle qui est **allocator** par défaut. La construction d'un conteneur avec un allocateur personnalisé permet de contrôler l'allocation et la libération des éléments de ce conteneur.  
  
 Par exemple, un objet allocateur peut allouer du stockage sur un segment de mémoire privé ou dans la mémoire partagée, ou il peut optimiser la mémoire pour les objets de petite ou de grande taille. Il peut également spécifier, via les définitions de types qu'il fournit, que les éléments soient accessibles via des objets d'accesseur spéciaux qui gèrent la mémoire partagée, ou effectuer un nettoyage de la mémoire automatique. Ainsi, une classe qui alloue du stockage à l'aide d'un objet allocateur doit utiliser ces types pour déclarer des objets de pointeurs et de référence, comme les conteneurs dans la bibliothèque C\+\+ standard.  
  
 **\(C\_\+\+98\/03 uniquement\)**Quand vous dérivez de la classe d'allocateur, vous devez fournir un struct [rebind](../Topic/allocator::rebind.md), dont le typedef `_Other` fait référence à votre classe nouvellement dérivée.  
  
 Ainsi, un allocateur définit les types suivants :  
  
-   [pointer](../Topic/allocator::pointer.md) se comporte comme un pointeur vers **Type**.  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md) se comporte comme un pointeur const vers **Type**.  
  
-   [reference](../Topic/allocator::reference.md) se comporte comme une référence à **Type**.  
  
-   [const\_reference](../Topic/allocator::const_reference.md) se comporte comme une référence const à **Type**.  
  
 Ces **Type**s spécifient la forme que les pointeurs et les références doivent assumer pour les éléments alloués. \([allocator::pointer](../Topic/allocator::pointer.md) n'est pas nécessairement identique à **Type**\* pour tous les objets d'allocateur, même s'il a cette définition évidente pour la classe **allocator**.\)  
  
 **C\+\+11 et versions ultérieures :**  pour autoriser les opérations de déplacement dans votre allocateur, utilisez l'interface d'allocateur minimale et implémentez le constructeur de copie, les opérateurs \=\= et \!\=, allocate et deallocate. Pour plus d'informations et pour obtenir un exemple, consultez [Allocateurs](../standard-library/allocators.md).  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[allocator](../Topic/allocator::allocator.md)|Constructeurs utilisés pour créer des objets `allocator`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator::const_pointer.md)|Type qui fournit un pointeur constant vers le type d'objet géré par l'allocateur.|  
|[const\_reference](../Topic/allocator::const_reference.md)|Type qui fournit une référence constante au type d'objet géré par l'allocateur.|  
|[difference\_type](../Topic/allocator::difference_type.md)|Type intégral signé qui peut représenter la différence entre des valeurs de pointeurs vers le type d'objet géré par l'allocateur.|  
|[pointer](../Topic/allocator::pointer.md)|Type qui fournit un pointeur vers le type d'objet géré par l'allocateur.|  
|[référence](../Topic/allocator::reference.md)|Type qui fournit une référence au type d'objet géré par l'allocateur.|  
|[type\_taille](../Topic/allocator::size_type.md)|Type intégral non signé qui peut représenter la longueur d'une séquence qu'un objet de classe de modèle `allocator` peut allouer.|  
|[value\_type](../Topic/allocator::value_type.md)|Type géré par l'allocateur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[adresse](../Topic/allocator::address.md)|Recherche l'adresse d'un objet dont la valeur est spécifiée.|  
|[allocate](../Topic/allocator::allocate.md)|Alloue un bloc de mémoire suffisamment grand pour stocker au moins un nombre spécifié d'éléments.|  
|[construct](../Topic/allocator::construct.md)|Construit un type d'objet spécifique à une adresse spécifiée qui est initialisée avec une valeur spécifiée.|  
|[deallocate](../Topic/allocator::deallocate.md)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[destroy](../Topic/allocator::destroy.md)|Appelle un destructeur d'objets sans libérer la mémoire où l'objet était stocké.|  
|[max\_size](../Topic/allocator::max_size.md)|Retourne le nombre d'éléments de type `Type` qui pourraient être alloués par un objet de classe `allocator` avant que la mémoire libre soit complètement utilisée.|  
|[rebind](../Topic/allocator::rebind.md)|Structure qui permet à un allocateur d'objets d'un type d'allouer du stockage pour les objets d'un autre type.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/allocator::operator=.md)|Assigne un objet `allocator` à un autre objet `allocator`.|  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)