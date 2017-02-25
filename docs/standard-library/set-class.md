---
title: "set, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::set"
  - "set"
  - "set/std::set"
  - "std.set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set (classe)"
ms.assetid: 8991f9aa-5509-4440-adc1-371512d32018
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# set, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de conteneur STL "set" est utilisée pour le stockage et la récupération des données d'une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés, en fonction des données qui sont automatiquement triées.  La valeur d'un élément appartenant à une classe set ne peut pas être modifiée directement.  Vous devez supprimer les anciennes valeurs et insérer les éléments ayant de nouvelles valeurs.  
  
## Syntaxe  
  
```  
template <  
    class Key,   
    class Traits=less<Key>,   
    class Allocator=allocator<Key>   
>  
class set  
```  
  
#### Paramètres  
 `Key`  
 Type de données d'élément à stocker dans la classe set.  
  
 `Traits`  
 Type qui fournit un objet de fonction pouvant comparer deux valeurs d'éléments comme clés de tri afin de déterminer leur ordre relatif dans la classe set.  Cet argument est facultatif et le prédicat binaire **less***\<Key\>* est la valeur par défaut.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, voir [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire de la classe set.  Cet argument est facultatif et sa valeur par défaut est **allocator***\<Key\>.*  
  
## Notes  
 Une classe set STL est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  C'est également un conteneur associatif simple, car les valeurs de ses éléments sont ses valeurs de clés.  
  
-   Réversible, car elle fournit un itérateur bidirectionnel pour accéder à ses éléments  
  
-   Triée, car les éléments sont classés par valeur de clé au sein du conteneur, selon une fonction de comparaison spécifiée.  
  
-   Unique dans le sens où chacun de ses éléments doit avoir une clé unique.  Étant donné qu'il s'agit également d'un conteneur associatif simple, ses éléments sont également uniques.  
  
 Une classe set est également décrite comme une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type de données contenues comme éléments ou comme clés.  Le type de données à utiliser est spécifié comme paramètre dans le modèle de la classe, avec la fonction de comparaison et l'allocateur.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces, car elles les exécutent en un temps qui est, en moyenne, proportionnel au logarithme du nombre d'éléments dans le conteneur.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 La classe set doit être sélectionnée comme conteneur associatif lorsque les conditions associant les valeurs à leurs clés sont remplies par l'application.  Les éléments d'une classe set sont uniques et agissent comme leurs propres clés de tri.  Pour ce type de structure, il peut s'agir d'une liste triée de mots qui ne peuvent apparaître qu'une seule fois.  Si de multiples occurrences de mots sont autorisées, il convient d'utiliser une classe multiset comme structure de conteneur.  Si les valeurs doivent être jointes à une liste de mots clés uniques, il convient d'utiliser une classe map comme conteneur de données.  Si les clés ne sont pas uniques, c'est une classe multimap qu'il convient d'utiliser comme conteneur.  
  
 La classe set trie la séquence qu'elle contrôle en appelant un objet de fonction stocké de type [key\_compare](../Topic/set::key_compare.md).  Cet objet stocké est une fonction de comparaison à laquelle il est possible d'accéder en appelant la fonction membre [key\_comp](../Topic/set::key_comp.md).  En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Cela entraîne le tri des éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire *f*\(*x,y*\) est un objet de fonction qui a deux objets d'arguments *x* et *y*, et la valeur de retour **true** ou **false**.  Un tri appliqué à un ensemble est un ordre faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive \(où deux objets *x* et *y* sont définis comme équivalents lorsque *f*\(*x,y*\) et *f*\(*y,x*\) ont la valeur false\).  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, voir [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
 L'itérateur fourni par la classe set est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/set::insert.md) et [set](../Topic/set::set.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications de fonctionnalités sont minimales par rapport à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre ensemble de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un jeu minimal de fonctionnalités, mais c'est suffisant pour pouvoir parler de plage d'itérateurs \(`First`, `Last`\) dans le contexte des fonctions membres de la classe.  
  
### Constructeurs  
  
|||  
|-|-|  
|[définir](../Topic/set::set.md)|Construit une classe set vide ou une copie de l'ensemble ou d'une partie d'une autre classe set.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/set::allocator_type.md)|Type qui représente la classe `allocator` pour l'objet set.|  
|[const\_iterator](../Topic/set::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans une classe set.|  
|[const\_pointer](../Topic/set::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` d'une classe set.|  
|[const\_reference](../Topic/set::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans une classe set pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/set::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans la classe set.|  
|[difference\_type](../Topic/set::difference_type.md)|Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'une classe set au sein d'une plage, parmi les éléments pointés par les itérateurs.|  
|[iterator](../Topic/set::iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'une classe set.|  
|[key\_compare](../Topic/set::key_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments au sein d'une classe set.|  
|[key\_type](../Topic/set::key_type.md)|Ce type décrit un objet stocké en tant qu'élément d'une classe set en sa qualité de clé de tri.|  
|[pointer](../Topic/set::pointer.md)|Type qui fournit un pointeur vers un élément d'une classe set.|  
|[référence](../Topic/set::reference.md)|Type qui fournit une référence à un élément stocké dans une classe set.|  
|[reverse\_iterator](../Topic/set::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'une classe set inversée.|  
|[type\_taille](../Topic/set::size_type.md)|Type entier non signé qui peut représenter le nombre d'éléments d'une classe set.|  
|[value\_compare](../Topic/set::value_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux éléments comme clés de tri pour déterminer leur ordre relatif dans la classe set.|  
|[value\_type](../Topic/set::value_type.md)|Ce type décrit un objet stocké en tant qu'élément d'une classe set en sa capacité en tant que valeur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/set::begin.md)|Retourne un itérateur qui traite le premier élément d'une classe set.|  
|[cbegin](../Topic/set::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'une classe set.|  
|[cend](../Topic/set::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'une classe set.|  
|[effacer](../Topic/set::clear.md)|Efface tous les éléments d'une classe set.|  
|[count](../Topic/set::count.md)|Retourne le nombre d'éléments d'une classe set dont la clé correspond à une clé spécifiée par un paramètre.|  
|[crbegin](../Topic/set::rbegin.md)|Retourne un itérateur const qui traite le premier élément d'un ensemble inversé.|  
|[crend](../Topic/set::rend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un ensemble inversé.|  
|[emplace](../Topic/set::emplace.md)|Insère un élément construit sur place dans une classe set.|  
|[emplace\_hint](../Topic/set::emplace_hint.md)|Insère un élément construit sur place dans une classe set, avec un indicateur de positionnement.|  
|[vide](../Topic/set::empty.md)|Vérifie si une classe set est vide.|  
|[end](../Topic/set::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une classe set.|  
|[equal\_range](../Topic/set::equal_range.md)|Retourne une paire d'itérateurs, respectivement, au premier élément d'une classe set possédant une clé supérieure à celle spécifiée, et au premier élément d'une classe set possédant une clé supérieure ou égale à la clé spécifiée.|  
|[erase](../Topic/set::erase.md)|Supprime d'un emplacement spécifié un élément ou une plage d'éléments compris dans une classe set ou supprime les éléments qui correspondent à une clé spécifiée.|  
|[find](../Topic/set::find.md)|Retourne un itérateur qui traite le premier emplacement d'un élément d'une classe set possédant une clé équivalente à une clé spécifiée.|  
|[get\_allocator](../Topic/set::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire la classe set.|  
|[insérer](../Topic/set::insert.md)|Insère un élément ou une plage d'éléments dans une classe set.|  
|[key\_comp](../Topic/set::key_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les clés au sein d'une classe set.|  
|[lower\_bound](../Topic/set::lower_bound.md)|Retourne un itérateur au premier élément d'une classe set avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[max\_size](../Topic/set::max_size.md)|Retourne la longueur maximale de la classe set.|  
|[rbegin](../Topic/set::rbegin.md)|Retourne un itérateur qui traite le premier élément d'une classe set inversée.|  
|[rend](../Topic/set::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une classe set inversée.|  
|[size](../Topic/set::size.md)|Retourne le nombre d'éléments figurant dans le jeu.|  
|[échange](../Topic/set::swap.md)|Échange les éléments de deux classes set.|  
|[upper\_bound](../Topic/set::upper_bound.md)|Retourne un itérateur au premier élément d'une classe set avec une valeur de clé supérieure à celle de la clé spécifiée.|  
|[value\_comp](../Topic/set::value_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les valeurs d'éléments d'une classe set.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/set::operator=.md)|Remplace les éléments d'une classe set par une copie d'une autre classe set.|  
  
## Configuration requise  
 **En\-tête :** \<set\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<set\>](../standard-library/set.md)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)