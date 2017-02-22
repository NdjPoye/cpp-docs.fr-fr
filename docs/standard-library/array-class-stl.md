---
title: "array, classe (STL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "array/std::tr1::array"
  - "std.tr1.array"
  - "array"
  - "std::tr1::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array (classe) (TR1)"
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# array, classe (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle une séquence de longueur `N` constituée d'éléments de type `Ty`.  La séquence est stockée comme tableau de `Ty`, contenu dans l'objet `array<Ty, N>`.  
  
## Syntaxe  
  
```  
template<class Ty, std::size_t N>  
    class array;  
```  
  
#### Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Ty`|Type d'un élément.|  
|`N`|Nombre d'éléments.|  
  
## Membres  
  
|||  
|-|-|  
|Définition de types|Description|  
|[array::const\_iterator](../Topic/array::const_iterator.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[array::const\_pointer](../Topic/array::const_pointer.md)|Type d'un pointeur constant vers un élément.|  
|[array::const\_reference](../Topic/array::const_reference.md)|Type d'une référence constante à un élément.|  
|[array::const\_reverse\_iterator](../Topic/array::const_reverse_iterator.md)|Type d'un itérateur inserve constant pour la séquence contrôlée.|  
|[array::difference\_type](../Topic/array::difference_type.md)|Type d'une distance signée entre deux éléments.|  
|[array::iterator](../Topic/array::iterator.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[array::pointer](../Topic/array::pointer.md)|Type d'un pointeur vers un élément.|  
|[array::reference](../Topic/array::reference.md)|Type d'une référence à un élément.|  
|[array::reverse\_iterator](../Topic/array::reverse_iterator.md)|Type d'un itérateur inverse pour la séquence contrôlée.|  
|[array::size\_type](../Topic/array::size_type.md)|Type d'une distance non signée entre deux éléments.|  
|[array::value\_type](../Topic/array::value_type.md)|Type d'un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[array::array](../Topic/array::array.md)|Construit un objet tableau.|  
|[array::assign](../Topic/array::assign.md)|Remplace tous les éléments.|  
|[array::at](../Topic/array::at.md)|Accède à un élément à une position spécifiée.|  
|[array::back](../Topic/array::back.md)|Accède au dernier élément.|  
|[array::begin](../Topic/array::begin.md)|Désigne le début de la séquence contrôlée.|  
|[array::cbegin](../Topic/array::cbegin.md)|Retourne un itérateur const à accès aléatoire pointant vers le premier élément du tableau.|  
|[array::cend](../Topic/array::cend.md)|Retourne un itérateur à accès aléatoire qui pointe juste après la fin du tableau.|  
|[array::crbegin](../Topic/array::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un tableau inversé.|  
|[array::crend](../Topic/array::crend.md)|Retourne un itérateur const qui pointe vers la fin d'un tableau inversé.|  
|[array::data](../Topic/array::data.md)|Obtient l'adresse du premier élément.|  
|[array::empty](../Topic/array::empty.md)|Vérifie la présence d'éléments.|  
|[array::end](../Topic/array::end.md)|Désigne la fin de la séquence contrôlée.|  
|[array::fill](../Topic/array::fill.md)|Remplace tous les éléments par une valeur spécifiée.|  
|[array::front](../Topic/array::front.md)|Accède au premier élément.|  
|[array::max\_size](../Topic/array::max_size.md)|Compte le nombre d'éléments.|  
|[array::rbegin](../Topic/array::rbegin.md)|Désigne le début de la séquence contrôlée inverse.|  
|[array::rend](../Topic/array::rend.md)|Désigne la fin de la séquence contrôlée inverse.|  
|[array::size](../Topic/array::size.md)|Compte le nombre d'éléments.|  
|[array::swap](../Topic/array::swap.md)|Échange le contenu de deux conteneurs.|  
  
|||  
|-|-|  
|Opérateur|Description|  
|[array::operator\=](../Topic/array::operator=.md)|Remplace la séquence contrôlée.|  
|[array::operator](../Topic/array::operator.md)|Accède à un élément à une position spécifiée.|  
  
## Notes  
 Le type a un constructeur par défaut `array()` et un opérateur d'assignation par défaut `operator=`, et il satisfait aux conditions requises pour un `aggregate`.  Par conséquent, les objets de type `array<Ty, N>` peuvent être initialisés à l'aide d'un initialiseur d'agrégat.  Par exemple :  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 crée l'objet `ai` qui contient quatre valeurs entières, initialise les trois premiers éléments respectivement aux valeurs 1, 2 et 3, et initialise le quatrième élément à la valeur 0.  
  
## Configuration requise  
 **En\-tête :** \<array\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<array\>](../standard-library/array.md)