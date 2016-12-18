---
title: "list, classe | Microsoft Docs"
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
  - "std.list"
  - "list"
  - "std::list"
  - "list/std::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list (classe)"
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# list, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de liste STL est une classe de modèle de conteneurs de séquences. Ces derniers conservent leurs éléments dans une disposition linéaire, et permettent des insertions et des suppressions efficaces à n'importe quel emplacement de la séquence.  La séquence est stockée sous forme de liste liée bidirectionnelle d'éléments, chacun contenant un membre d'un type *Type*.  
  
## Syntaxe  
  
```cpp  
  
template <    class Type,     class Allocator=allocator<Type>  > class list  
```  
  
#### Paramètres  
 *Type*  
 Type de données d'élément à stocker dans la liste.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la libération de mémoire de la liste.  Cet argument est facultatif et sa valeur par défaut est **allocator**\<*Type*\>*.*  
  
## Notes  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les vecteurs doivent être le conteneur par défaut pour la gestion d'une séquence quand l'accès aléatoire à n'importe quel élément est primordial et que des insertions ou des suppressions d'éléments sont seulement nécessaires à la fin d'une séquence.  Les performances du conteneur de classe deque sont supérieures quand l'accès aléatoire est nécessaire, et que les insertions et suppressions au début et à la fin d'une séquence sont cruciales.  
  
 Les fonctions membres de liste [merge](../Topic/list::merge.md), [reverse](../Topic/list::reverse.md), [unique](../Topic/list::unique.md), [remove](../Topic/list::remove.md) et [remove\_if](../Topic/list::remove_if.md) ont été optimisées pour le traitement des objets de liste. En outre, elles offrent une alternative de haute performance à leurs homologues génériques.  
  
 La réallocation de liste se produit quand une fonction membre doit insérer ou effacer des éléments de la liste.  Dans ce cas, seuls les itérateurs ou les références qui pointent vers les parties effacées de la séquence contrôlée deviennent non valides.  
  
 Incluez l'en\-tête standard STL \<list\> pour définir la liste de classes de modèles du [conteneur](../standard-library/stl-containers.md) et plusieurs modèles de prise en charge.  
  
### Constructeurs  
  
|||  
|-|-|  
|[list](../Topic/list::list.md)|Construit une liste de taille spécifique ou contenant des éléments de valeurs spécifiques, ou contenant un `allocator` spécifique ou comme copie d'une autre liste.|  
  
### Typedef  
  
|||  
|-|-|  
|[allocator\_type](../Topic/list::allocator_type.md)|Type qui représente la classe `allocator` d'un objet list.|  
|[const\_iterator](../Topic/list::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans une liste.|  
|[const\_pointer](../Topic/list::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans une liste.|  
|[const\_reference](../Topic/list::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans une liste pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/list::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans une liste.|  
|[difference\_type](../Topic/list::difference_type.md)|Type qui fournit la différence entre deux itérateurs qui font référence aux éléments d'une même liste.|  
|[iterator](../Topic/list::iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou modifier un élément d'une liste.|  
|[pointer](../Topic/list::pointer.md)|Type qui fournit un pointeur vers un élément d'une liste.|  
|[référence](../Topic/list::reference.md)|Type qui fournit une référence à un élément `const` stocké dans une liste pour la lecture et l'exécution des opérations `const`.|  
|[reverse\_iterator](../Topic/list::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel pouvant lire ou modifier un élément d'une liste inversée.|  
|[type\_taille](../Topic/list::size_type.md)|Type qui compte le nombre d'éléments dans une liste.|  
|[value\_type](../Topic/list::value_type.md)|Type qui représente le type de données stocké dans une liste.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[assign](../Topic/list::assign.md)|Efface les éléments d'une liste et copie un nouvel ensemble d'éléments dans la liste cible.|  
|[back](../Topic/list::back.md)|Retourne une référence au dernier élément d'une liste.|  
|[begin](../Topic/list::begin.md)|Retourne un itérateur qui traite le premier élément d'une liste.|  
|[list::cbegin](../Topic/list::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'une liste.|  
|[list::cend](../Topic/list::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'une liste.|  
|[list::clear](../Topic/list::clear.md)|Efface tous les éléments d'une liste.|  
|[list::crbegin](../Topic/list::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'une liste inversée.|  
|[list::crend](../Topic/list::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'une liste inversée.|  
|[list::emplace](../Topic/list::emplace.md)|Insère un élément construit en place dans une liste à la position spécifiée.|  
|[list::emplace\_back](../Topic/list::emplace_back.md)|Ajoute un élément construit sur place à la fin d'une liste.|  
|[list::emplace\_front](../Topic/list::emplace_front.md)|Ajoute un élément construit sur place au début d'une liste.|  
|[empty](../Topic/list::empty.md)|Vérifie si une liste est vide.|  
|[end](../Topic/list::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une liste.|  
|[erase](../Topic/list::erase.md)|Supprime un élément ou une plage d'éléments d'une liste aux emplacements spécifiés.|  
|[front](../Topic/list::front.md)|Retourne une référence au premier élément d'une liste.|  
|[get\_allocator](../Topic/list::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire une liste.|  
|[insert](../Topic/list::insert.md)|Insère un élément, un certain nombre d'éléments ou une plage d'éléments dans une liste à la position spécifiée.|  
|[max\_size](../Topic/list::max_size.md)|Retourne la longueur maximale d'une liste.|  
|[merge](../Topic/list::merge.md)|Supprime les éléments de la liste d'arguments, les insère dans la liste cible, puis classe le nouvel ensemble combiné d'éléments dans l'ordre croissant ou dans un autre ordre spécifique.|  
|[pop\_back](../Topic/list::pop_back.md)|Supprime l'élément à la fin d'une liste.|  
|[pop\_front](../Topic/list::pop_front.md)|Supprime l'élément au début d'une liste.|  
|[push\_back](../Topic/list::push_back.md)|Ajoute un élément à la fin d'une liste.|  
|[push\_front](../Topic/list::push_front.md)|Ajoute un élément au début d'une liste.|  
|[rbegin](../Topic/list::rbegin.md)|Retourne un itérateur qui traite le premier élément d'une liste inversée.|  
|[remove](../Topic/list::remove.md)|Efface les éléments d'une liste qui correspondent à la valeur spécifiée.|  
|[remove\_if](../Topic/list::remove_if.md)|Efface les éléments de la liste pour laquelle un prédicat spécifié est satisfait.|  
|[rend](../Topic/list::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une liste inversée.|  
|[resize](../Topic/list::resize.md)|Spécifie une nouvelle taille pour une liste.|  
|[reverse](../Topic/list::reverse.md)|Inverse l'ordre dans lequel les éléments apparaissent dans une liste.|  
|[size](../Topic/list::size.md)|Retourne le nombre d'éléments d'une liste.|  
|[sort](../Topic/list::sort.md)|Réorganise les éléments d'une liste dans l'ordre croissant ou en fonction d'une autre relation d'ordre.|  
|[splice](../Topic/list::splice.md)|Supprime des éléments de la liste d'arguments et les insère dans la liste cible.|  
|[échange](../Topic/list::swap.md)|Échange les éléments de deux listes.|  
|[unique](../Topic/list::unique.md)|Supprime les doublons adjacents ou les éléments adjacents qui satisfont un autre prédicat binaire dans la liste.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[list::operator\=](../Topic/list::operator=.md)|Remplace les éléments de la liste par une copie d'une autre liste.|  
  
## Configuration requise  
 **En\-tête** : \<list\>  
  
## Voir aussi  
 [\<list\>](../standard-library/list.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)