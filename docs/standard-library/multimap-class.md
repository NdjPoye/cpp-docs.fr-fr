---
title: "multimap, classe | Microsoft Docs"
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
  - "multimap"
  - "std.multimap"
  - "map/std::multimap"
  - "std::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multimap (classe)"
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
caps.latest.revision: 23
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# multimap, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe multimap STL est utilisée pour le stockage et la récupération des données d'une collection dans laquelle chaque élément est une paire constituée d'une valeur de données et d'une clé de tri.  La valeur de la clé n'a pas besoin d'être unique. En outre, elle est utilisée pour le tri automatique des données.  La valeur d'un élément d'une classe multimap peut être modifiée directement, mais pas la valeur de clé qui lui est associée.  Les valeurs de clés associées aux anciens éléments doivent être supprimées, et de nouvelles valeurs de clés doivent être associées aux nouveaux éléments insérés.  
  
## Syntaxe  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class multimap;  
```  
  
#### Paramètres  
 `Key`  
 Type de données clé à stocker dans la classe multimap.  
  
 `Type`  
 Type de données d'élément à stocker dans la classe multimap.  
  
 `Traits`  
 Type qui fournit un objet de fonction pouvant comparer deux valeurs d'éléments comme clés de tri afin de déterminer leur ordre relatif dans la classe multimap.  Le prédicat binaire `less<Key>` est la valeur par défaut.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, consultez [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire de la classe map.  Cet argument est facultatif et sa valeur par défaut est `allocator<pair <const Key, Type> >`.  
  
## Notes  
 La classe multimap STL est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  
  
-   Réversible, car elle fournit des itérateurs bidirectionnels pour accéder à ses éléments.  
  
-   Triée, car les éléments sont classés par valeur de clé au sein du conteneur, selon une fonction de comparaison spécifiée.  
  
-   Multiple, car il n'est pas nécessaire que ses éléments possèdent des clés uniques, ce qui permet à une valeur de clé d'être associée à plusieurs valeurs de données d'éléments.  
  
-   Un conteneur associatif de paires, car ses valeurs de données d'éléments sont séparées de ses valeurs de clés.  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type de données contenues comme éléments ou comme clés.  Les types de données utilisés pour les éléments et les clés sont eux spécifiés comme paramètres dans la classe de modèle avec la fonction de comparaison et l'allocateur.  
  
 L'itérateur fourni par la classe map est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/multimap::insert.md) et [multimap](../Topic/multimap::multimap.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications de fonctionnalités sont minimales par rapport à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre ensemble de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un jeu minimal de fonctionnalités, mais c'est suffisant pour pouvoir parler de plage d'itérateurs \(`[First, Last)`\) dans le contexte des fonctions membres de la classe.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces, car elles les exécutent en un temps qui est, en moyenne, proportionnel au logarithme du nombre d'éléments dans le conteneur.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 La classe multimap doit être sélectionnée comme conteneur associatif lorsque les conditions associant les valeurs à leurs clés sont remplies par l'application.  Pour ce type de structure, il peut s'agir d'une liste triée de mots clés avec des valeurs de chaîne associées fournissant par exemple des définitions, où les mots n'ont pas toujours été définis de manière unique.  Si, en revanche, les mots clés sont définis de manière unique afin que les clés soient uniques, il convient d'utiliser une classe map comme conteneur.  Si, en revanche, seule la liste de mots a été stockée, il convient d'utiliser une classe set comme conteneur.  Si de multiples occurrences de mots sont autorisées, il convient d'utiliser une classe multiset comme structure de conteneur.  
  
 La classe multimap trie la séquence qu'elle contrôle en appelant un objet de fonction stocké de type [key\_compare](../Topic/multimap::key_compare.md).  Cet objet stocké est une fonction de comparaison à laquelle il est possible d'accéder en appelant la fonction membre [key\_comp](../Topic/multimap::key_comp.md).  En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Cela entraîne le tri des éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire `f(x,y)` est un objet de fonction qui a deux objets d'argument `x` et `y`, et une valeur de retour true ou false.  Un tri appliqué à un ensemble est un ordre faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive, où deux objets `x` et `y` sont définis comme équivalents lorsque `f(x,y)` et `f(y,x)` sont false.  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, consultez [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[multimap](../Topic/multimap::multimap.md)|Construit un `multimap` vide ou une copie de l'ensemble ou d'une partie d'un autre `multimap`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/multimap::allocator_type.md)|Type qui représente la classe `allocator` pour l'objet `multimap`.|  
|[const\_iterator](../Topic/multimap::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans le `multimap`.|  
|[const\_pointer](../Topic/multimap::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un `multimap`.|  
|[const\_reference](../Topic/multimap::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans un `multimap` pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/multimap::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans le `multimap`.|  
|[difference\_type](../Topic/multimap::difference_type.md)|Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'un `multimap` au sein d'une plage, parmi les éléments pointés par les itérateurs.|  
|[iterator](../Topic/multimap::iterator.md)|Type qui fournit la différence entre deux itérateurs qui font référence aux éléments d'un même `multimap`.|  
|[key\_compare](../Topic/multimap::key_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments au sein d'un `multimap`.|  
|[key\_type](../Topic/multimap::key_type.md)|Type qui décrit l'objet de clé de tri qui constitue chaque élément du `multimap`.|  
|[mapped\_type](../Topic/multimap::mapped_type.md)|Type qui représente le type de données stocké dans un `multimap`.|  
|[pointer](../Topic/multimap::pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un `multimap`.|  
|[référence](../Topic/multimap::reference.md)|Type qui fournit une référence à un élément stocké dans un `multimap`.|  
|[reverse\_iterator](../Topic/multimap::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'un `multimap` inversé.|  
|[type\_taille](../Topic/multimap::size_type.md)|Type entier non signé qui fournit un pointeur vers un élément `const` d'un `multimap`.|  
|[value\_type](../Topic/multimap::value_type.md)|Type qui fournit un objet de fonction pouvant comparer deux éléments comme clés de tri pour déterminer leur ordre relatif dans le `multimap`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/multimap::begin.md)|Retourne un itérateur traitant le premier élément d'un `multimap`.|  
|[cbegin](../Topic/multimap::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `multimap`.|  
|[cend](../Topic/multimap::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'un `multimap`.|  
|[effacer](../Topic/multimap::clear.md)|Efface tous les éléments d'un `multimap`.|  
|[count](../Topic/multimap::count.md)|Retourne le nombre d'éléments d'un `multimap` dont la clé correspond à une clé spécifiée par un paramètre.|  
|[crbegin](../Topic/multimap::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `multimap` inversé.|  
|[crend](../Topic/multimap::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un `multimap` inversé.|  
|[emplace](../Topic/multimap::emplace.md)|Insère un élément construit sur place dans un `multimap`.|  
|[emplace\_hint](../Topic/multimap::emplace_hint.md)|Insère un élément construit sur place dans un `multimap`, avec un indicateur de positionnement.|  
|[vide](../Topic/multimap::empty.md)|Vérifie si un `multimap` est vide.|  
|[end](../Topic/multimap::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `multimap`.|  
|[equal\_range](../Topic/multimap::equal_range.md)|Recherche la plage d'éléments dans laquelle se trouve une clé d'élément correspondant à une valeur spécifiée.|  
|[erase](../Topic/multimap::erase.md)|Supprime d'un emplacement spécifié un élément ou une plage d'éléments compris dans un `multimap` ou supprime les éléments qui correspondent à une clé spécifiée.|  
|[find](../Topic/multimap::find.md)|Retourne un itérateur qui traite le premier emplacement d'un élément dans un `multimap` possédant une clé équivalente à une clé spécifiée.|  
|[get\_allocator](../Topic/multimap::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire le `multimap`.|  
|[insérer](../Topic/multimap::insert.md)|Insère un élément ou une plage d'éléments dans un `multimap`.|  
|[key\_comp](../Topic/multimap::key_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les clés au sein d'un `multimap`.|  
|[lower\_bound](../Topic/multimap::lower_bound.md)|Retourne un itérateur au premier élément d'un `multimap` avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[max\_size](../Topic/multimap::max_size.md)|Retourne la longueur maximale du `multimap`.|  
|[rbegin](../Topic/multimap::rbegin.md)|Retourne un itérateur qui traite le premier élément d'un `multimap` inversé.|  
|[rend](../Topic/multimap::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `multimap` inversé.|  
|[size](../Topic/multimap::size.md)|Retourne le nombre d'éléments d'un `multimap`.|  
|[échange](../Topic/multimap::swap.md)|Échange les éléments de deux `multimap`.|  
|[upper\_bound](../Topic/multimap::upper_bound.md)|Retourne un itérateur au premier élément d'un `multimap` avec une valeur de clé supérieure à celle de la clé spécifiée.|  
|[value\_comp](../Topic/multimap::value_comp.md)|La fonction membre retourne un objet de fonction qui détermine l'ordre des éléments d'un `multimap` en comparant leurs valeurs de clés.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/multimap::operator=.md)|Remplace les éléments d'un `multimap` par une copie d'un autre `multimap`.|  
  
## Configuration requise  
 **En\-tête :** \<map\>  
  
 **Espace de noms :** std  
  
 Les paires \(**clé**, **valeur**\) sont stockées dans une classe multimap en tant qu'objets de type `pair`.  La classe pair nécessite l'en\-tête \<utility\>, qui est inclus automatiquement par \<map\>.  
  
## Voir aussi  
 [\<map\> Members](http://msdn.microsoft.com/fr-fr/7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)