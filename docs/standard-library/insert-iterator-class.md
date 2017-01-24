---
title: "insert_iterator, classe | Microsoft Docs"
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
  - "std::insert_iterator"
  - "iterator/std::insert_iterator"
  - "std.insert_iterator"
  - "insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert_iterator (classe)"
  - "insert_iterator (classe), syntaxe"
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# insert_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un adaptateur d'itérateur qui répond aux exigences d'un itérateur de sortie.  Elle insère, plutôt que remplace, des éléments dans une séquence et fournit ainsi une sémantique différente de la sémantique de remplacement fournie par les itérateurs de la séquence C\+\+ et les conteneurs associatifs.  La classe `insert_iterator` est mise en modèle sur le type de conteneur qui est adapté.  
  
## Syntaxe  
  
```  
template <class Container> class insert_iterator;  
```  
  
#### Paramètres  
 `Container`  
 Type de conteneur dans lequel des éléments doivent être insérés par un `insert_iterator`.  
  
## Notes  
 Le conteneur de type **Conteneur** doit être conforme aux spécifications d'un conteneur de taille variable et posséder une fonction membre d'insertion de deux arguments dont les paramètres sont de type **Container::iterator** et **Container::value\_type** et qui retourne un type **Container::iterator**.  La séquence STL \(Standard Template Library\) et les conteneurs associatifs triés sont conformes à ces spécifications et peuvent être adaptés pour être utilisés avec des objets `insert_iterator`.  Pour les conteneurs associatifs, l'argument de position est traité comme un indice, lequel peut améliorer ou dégrader les performances selon sa qualité.  Un `insert_iterator` doit toujours être initialisé avec son conteneur.  
  
### Constructeurs  
  
|||  
|-|-|  
|[insert\_iterator](../Topic/insert_iterator::insert_iterator.md)|Construit un `insert_iterator` qui insère un élément à une position spécifiée dans un conteneur.|  
  
### Typedef  
  
|||  
|-|-|  
|[container\_type](../Topic/insert_iterator::container_type.md)|Type qui représente le conteneur dans lequel une insertion générale doit être effectuée.|  
|[référence](../Topic/insert_iterator::reference.md)|Type qui fournit une référence à un élément dans une séquence contrôlée par le conteneur associé.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/insert_iterator::operator*.md)|Opérateur de suppression de référence utilisé pour implémenter l'expression de l'itérateur de sortie \*`i` \= `x` pour une insertion générale.|  
|[operator\+\+](../Topic/insert_iterator::operator++.md)|Incrémente le `insert_iterator` à l'emplacement suivant où une valeur peut être stockée.|  
|[operator\=](../Topic/insert_iterator::operator=.md)|Opérateur d'assignation servant à implémenter l'expression de l'itérateur de sortie \*`i` \= `x` pour une insertion générale.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)