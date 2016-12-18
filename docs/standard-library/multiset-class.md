---
title: "multiset, classe | Microsoft Docs"
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
  - "std::multiset"
  - "set/std::multiset"
  - "std.multiset"
  - "multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiset (classe)"
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
caps.latest.revision: 21
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# multiset, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe multiset STL est utilisée pour le stockage et la récupération des données d'une collection dans laquelle les valeurs des éléments n'ont pas besoin d'être uniques, et où ces dernières servent de valeurs de clés en fonction desquelles les données sont automatiquement triées.  La valeur de clé d'un élément appartenant à une classe multiset ne peut pas être modifiée directement.  En effet, les anciennes valeurs doivent être supprimées et les éléments ayant une nouvelle valeur doivent être insérés.  
  
## Syntaxe  
  
```  
  
        template <  
   class Key,   
   class Compare=less<Key>,   
   class Allocator=allocator<Key>   
>  
class multiset  
```  
  
#### Paramètres  
 *Clé*  
 Type de données d'élément à stocker dans la classe multiset.  
  
 *Comparaison*  
 Type qui fournit un objet de fonction pouvant comparer deux valeurs d'éléments comme clés de tri afin de déterminer leur ordre relatif dans la classe multiset.  Le prédicat binaire **less**\<Key\> est la valeur par défaut.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, consultez [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire de la classe multiset.  La valeur par défaut est **allocator***\<Key\>.*  
  
## Notes  
 La classe multiset STL est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  
  
-   Réversible, car elle fournit des itérateurs bidirectionnels pour accéder à ses éléments.  
  
-   Triée, car les éléments sont classés par valeur de clé au sein du conteneur, selon une fonction de comparaison spécifiée.  
  
-   Multiple, car il n'est pas nécessaire que ses éléments aient des clés uniques. Une valeur de clé peut être associée à plusieurs valeurs d'éléments.  
  
-   Un conteneur associatif simple, car les valeurs de ses éléments sont ses valeurs de clés.  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type de données contenues comme éléments.  Le type de données à utiliser est spécifié comme paramètre dans le modèle de la classe, avec la fonction de comparaison et l'allocateur.  
  
 L'itérateur fourni par la classe multiset est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/multiset::insert.md) et [multiset](../Topic/multiset::multiset.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications de fonctionnalités sont minimales par rapport à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre ensemble de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un jeu minimal de fonctionnalités, mais c'est suffisant pour pouvoir parler de plage d'itérateurs \(`First`, `Last`\) dans le contexte des fonctions membres de la classe.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces, car elles les exécutent en un temps qui est, en moyenne, proportionnel au logarithme du nombre d'éléments dans le conteneur.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 La classe multiset doit être sélectionnée comme conteneur associatif lorsque les conditions associant les valeurs à leurs clés sont remplies par l'application.  Les éléments d'une classe multiset peuvent être nombreux et agir comme leurs propres clés de tri, afin d'éviter que les clés ne soient uniques.  Pour ce type de structure, il peut s'agir d'une liste triée de mots qui peuvent apparaître plusieurs fois.  Si les occurrences multiples de mots ne sont pas autorisées, c'est un ensemble qu'il convient d'utiliser comme structure de conteneur.  Si des définitions uniques sont jointes en tant que valeurs à la liste de mots clés uniques, c'est une classe map qu'il convient d'utiliser comme structure pour la contenance des données.  Si les définitions ne sont pas uniques, c'est une classe multimap qu'il convient d'utiliser comme conteneur.  
  
 La classe multiset organise la séquence qu'elle contrôle en appelant un objet de fonction stocké de type `Compare`.  Cet objet stocké est une fonction de comparaison à laquelle il est possible d'accéder en appelant la fonction membre [key\_comp](../Topic/multiset::key_comp.md).  En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Cela entraîne le tri des éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire *f*\(*x*,*y*\) est un objet de fonction qui a deux objets d'arguments *x* et *y*, et la valeur de retour **true** ou **false**.  Un tri appliqué à un ensemble est un ordre faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive \(où deux objets x et y sont définis comme équivalents lorsque *f*\(*x,y*\) et *f*\(*y,x*\) ont la valeur false\).  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, consultez [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
### Constructeurs  
  
|||  
|-|-|  
|[multiset](../Topic/multiset::multiset.md)|Construit un `multiset` vide ou une copie de l'ensemble ou d'une partie d'un `multiset` spécifié.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/multiset::allocator_type.md)|Typedef pour la classe `allocator` de l'objet `multiset`.|  
|[const\_iterator](../Topic/multiset::const_iterator.md)|Typedef pour un itérateur bidirectionnel qui peut lire un élément `const` dans le `multiset`.|  
|[const\_pointer](../Topic/multiset::const_pointer.md)|Typedef pour un pointeur vers un élément `const` dans un `multiset`.|  
|[const\_reference](../Topic/multiset::const_reference.md)|Typedef pour une référence à un élément `const` stocké dans un `multiset` pour lire et effectuer des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/multiset::const_reverse_iterator.md)|Typedef pour un itérateur bidirectionnel qui peut lire n'importe quel élément `const` dans le `multiset`.|  
|[difference\_type](../Topic/multiset::difference_type.md)|Typedef entier signé pour le nombre d'éléments d'un `multiset` compris dans une plage d'éléments pointés par des itérateurs.|  
|[iterator](../Topic/multiset::iterator.md)|Typedef pour un itérateur bidirectionnel qui permet de lire ou de modifier tout élément d'un `multiset`.|  
|[key\_compare](../Topic/multiset::key_compare.md)|Typedef pour un objet de fonction qui peut comparer deux clés pour déterminer l'ordre relatif de deux éléments d'un `multiset`.|  
|[key\_type](../Topic/multiset::key_type.md)|Typedef pour un objet de fonction qui peut comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments d'un `multiset`.|  
|[pointer](../Topic/multiset::pointer.md)|Typedef pour un pointeur vers un élément d'un `multiset`.|  
|[référence](../Topic/multiset::reference.md)|Typedef pour une référence à un élément stocké dans un `multiset`.|  
|[reverse\_iterator](../Topic/multiset::reverse_iterator.md)|Typedef pour un itérateur bidirectionnel qui permet de lire ou de modifier un élément d'un `multiset` inversé.|  
|[type\_taille](../Topic/multiset::size_type.md)|Type entier non signé qui peut représenter le nombre d'éléments dans un `multiset`.|  
|[value\_compare](../Topic/multiset::value_compare.md)|Typedef pour un objet de fonction qui peut comparer deux éléments en tant que clés de tri pour déterminer leur ordre relatif au sein d'un `multiset`.|  
|[value\_type](../Topic/multiset::value_type.md)|Typedef qui décrit un objet stocké en tant qu'élément comme un `multiset` par sa capacité en tant que valeur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/multiset::begin.md)|Retourne un itérateur qui pointe vers le premier élément d'un `multiset`.|  
|[cbegin](../Topic/multiset::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `multiset`.|  
|[cend](../Topic/multiset::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'un `multiset`.|  
|[effacer](../Topic/multiset::clear.md)|Efface tous les éléments d'un `multiset`.|  
|[count](../Topic/multiset::count.md)|Retourne le nombre d'éléments d'un `multiset` dont la clé correspond à celle spécifiée en tant que paramètre.|  
|[crbegin](../Topic/multiset::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un ensemble inversé.|  
|[crend](../Topic/multiset::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un ensemble inversé.|  
|[emplace](../Topic/multiset::emplace.md)|Insère un élément construit sur place dans un `multiset`.|  
|[emplace\_hint](../Topic/multiset::emplace_hint.md)|Insère un élément construit sur place dans un `multiset`, avec un indicateur de positionnement.|  
|[vide](../Topic/multiset::empty.md)|Vérifie si un `multiset` est vide.|  
|[end](../Topic/multiset::end.md)|Retourne un itérateur qui pointe vers l'emplacement situé après le dernier élément d'un `multiset`.|  
|[equal\_range](../Topic/multiset::equal_range.md)|Retourne une paire d'itérateurs.  Le premier itérateur de la paire pointe vers le premier élément d'un `multiset` avec une clé qui est supérieure à celle spécifiée.  Le deuxième itérateur de la paire pointe vers le premier élément du `multiset` avec une clé dont la valeur est supérieure ou égale à la clé spécifiée.|  
|[erase](../Topic/multiset::erase.md)|Supprime d'un emplacement spécifié un élément ou une plage d'éléments compris dans un `multiset` ou supprime les éléments qui correspondent à une clé spécifiée.|  
|[find](../Topic/multiset::find.md)|Retourne un itérateur qui pointe vers le premier emplacement d'un élément d'un `multiset` dont la clé est égale à la clé spécifiée.|  
|[get\_allocator](../Topic/multiset::get_allocator.md)|Retourne une copie de l'objet `allocator` qui est utilisé pour construire le `multiset`.|  
|[insérer](../Topic/multiset::insert.md)|Insère un élément ou une plage d'éléments dans un `multiset`.|  
|[key\_comp](../Topic/multiset::key_comp.md)|Fournit un objet de fonction qui peut comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments d'un `multiset`.|  
|[lower\_bound](../Topic/multiset::lower_bound.md)|Retourne un itérateur au premier élément d'un `multiset` avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[max\_size](../Topic/multiset::max_size.md)|Retourne la longueur maximale du `multiset`.|  
|[rbegin](../Topic/multiset::rbegin.md)|Retourne un itérateur qui pointe vers le premier élément d'un `multiset` inversé.|  
|[rend](../Topic/multiset::rend.md)|Retourne un itérateur qui pointe vers l'emplacement situé après le dernier élément d'un `multiset` inversé.|  
|[size](../Topic/multiset::size.md)|Retourne le nombre d'éléments contenus dans un `multiset`.|  
|[échange](../Topic/multiset::swap.md)|Échange les éléments de deux `multiset`.|  
|[upper\_bound](../Topic/multiset::upper_bound.md)|Retourne un itérateur au premier élément d'un `multiset` avec une valeur de clé supérieure à celle de la clé spécifiée.|  
|[value\_comp](../Topic/multiset::value_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les valeurs d'éléments dans un `multiset`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/multiset::operator=.md)|Remplace les éléments d'un `multiset` par une copie d'un autre `multiset`.|  
  
## Configuration requise  
 **En\-tête :** \<set\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<set\> Members](http://msdn.microsoft.com/fr-fr/0c2d57c0-173f-4204-b579-c5f06aad8b95)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)