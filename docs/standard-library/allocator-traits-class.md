---
title: "allocator_traits, classe | Microsoft Docs"
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
  - "memory/std::allocator_traits"
  - "memory/std::allocator_traits::propagate_on_container_move_assignment"
  - "memory/std::allocator_traits::const_pointer"
  - "memory/std::allocator_traits::propagate_on_container_swap"
  - "memory/std::allocator_traits::propagate_on_container_copy_assignment"
  - "memory/std::allocator_traits::difference_type"
  - "memory/std::allocator_traits::allocator_type"
  - "memory/std::allocator_traits::value_type"
  - "memory/std::allocator_traits::pointer"
  - "memory/std::allocator_traits::size_type"
  - "memory/std::allocator_traits::const_void_pointer"
  - "memory/std::allocator_traits::void_pointer"
dev_langs: 
  - "C++"
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_traits, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet que supplée *un type d'allocateur*.  Un type d'allocateur est n'importe quel type qui décrit un objet d'allocation qui permet de gérer le stockage alloué.  Spécifiquement, pour n'importe quel type `Alloc` d'allocateur, vous pouvez utiliser `allocator_traits<Alloc>` pour déterminer toutes les informations nécessaires par un conteneur activé pou les allocateurs.  Pour plus d'informations, consultez [allocator, classe](../standard-library/allocator-class.md).  
  
## Syntaxe  
  
```cpp  
template<class Alloc>  
    class allocator_traits;  
```  
  
### Typedef  
  
|Nom|Description|  
|---------|-----------------|  
|`allocator_traits::allocator_type`|Ce type est un synonyme du paramètre de modèle `Alloc`.|  
|`allocator_traits::const_pointer`|Ce type est `Alloc::const_pointer`, si ce type est de forme correcte ; sinon, ce type est `pointer_traits<pointer>::rebind<const value_type>`.|  
|`allocator_traits::const_void_pointer`|Ce type est `Alloc::const_void_pointer`, si ce type est de forme correcte ; sinon, ce type est `pointer_traits<pointer>::rebind<const void>`.|  
|`allocator_traits::difference_type`|Ce type est `Alloc::difference_type`, si ce type est de forme correcte ; sinon, ce type est `pointer_traits<pointer>::difference_type`.|  
|`allocator_traits::pointer`|Ce type est `Alloc::pointer`, si ce type est de forme correcte ; sinon, ce type est `value_type *`.|  
|`allocator_traits::propagate_on_container_copy_assignment`|Ce type est `Alloc::propagate_on_container_copy_assignment`, si ce type est de forme correcte ; sinon, ce type est `false_type`.|  
|`allocator_traits::propagate_on_container_move_assignment`|Ce type est `Alloc::propagate_on_container_move_assignment`, si ce type est de forme correcte ; sinon, ce type est `false_type`.  Si le type contient la valeur true, un conteneur activé pour les allocateurs copie l'allocateur stocké sur une attribution de déplacement.|  
|`allocator_traits::propagate_on_container_swap`|Ce type est `Alloc::propagate_on_container_swap`, si ce type est de forme correcte ; sinon, ce type est `false_type`.  Si le type contient la valeur true, un conteneur activé pour les allocateurs permute son allocateur stocké sur un échange.|  
|`allocator_traits::size_type`|Ce type est `Alloc::size_type`, si ce type est de forme correcte ; sinon, ce type est `make_unsigned<difference_type>::type`.|  
|`allocator_traits::value_type`|Le type est un synonyme de `Alloc::value_type`|  
|`allocator_traits::void_pointer`|Ce type est `Alloc::void_pointer`, si ce type est de forme correcte ; sinon, ce type est `pointer_traits<pointer>::rebind<void>`.|  
  
### Méthodes statiques  
 Les méthodes statiques suivantes appellent la méthode correspondante sur un paramètre donné d'allocateur.  
  
|Nom|Description|  
|---------|-----------------|  
|[allocator\_traits::allocate, méthode](../Topic/allocator_traits::allocate%20Method.md)|Méthode statique qui alloue la mémoire à l'aide du paramètre d'allocateur donné.|  
|[allocator\_traits::construct, méthode](../Topic/allocator_traits::construct%20Method.md)|Méthode statique qui utilise un allocateur spécifié pour construire un objet.|  
|[allocator\_traits::deallocate, méthode](../Topic/allocator_traits::deallocate%20Method.md)|Méthode statique qui utilise un allocateur spécifié pour désallouer un nombre spécifié d'objets.|  
|[allocator\_traits::destroy, méthode](../Topic/allocator_traits::destroy%20Method.md)|Méthode statique qui utilise un allocateur spécifié pour appeler le destructeur sur un objet sans libérer sa mémoire.|  
|[allocator\_traits::max\_size, méthode](../Topic/allocator_traits::max_size%20Method.md)|Méthode statique qui utilise un allocateur spécifié pour déterminer le nombre maximal d'objets qui peuvent être alloués.|  
|[allocator\_traits::select\_on\_container\_copy\_construction, méthode](../Topic/allocator_traits::select_on_container_copy_construction%20Method.md)|Méthode statique qui appelle `select_on_container_copy_construction` sur l'allocateur spécifié.|  
  
## Configuration requise  
 **En\-tête:** \<mémoire\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<memory\>](../standard-library/memory.md)   
 [pointer\_traits, struct](../standard-library/pointer-traits-struct.md)   
 [scoped\_allocator\_adaptor::construct, méthode](../standard-library/scoped-allocator-adaptor-class.md)