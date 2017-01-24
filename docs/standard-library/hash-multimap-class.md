---
title: "hash_multimap, classe | Microsoft Docs"
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
  - "stdext::hash_multimap"
  - "stdext.hash_multimap"
  - "hash_map/stdext::hash_multimap"
  - "hash_multimap"
  - "std::hash_multimap"
  - "std.hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multimap (classe)"
ms.assetid: f41a6db9-67aa-43a3-a3c5-dbfe9ec3ae7d
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash_multimap, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette API méthode est obsolète.  L'alternative est [unordered\_multimap, classe](../standard-library/unordered-multimap-class.md).  
  
 La classe conteneur hash\_multimap est une extension de STL, et elle est utilisée pour le stockage et la récupération rapide des données d'une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur ne doit pas être unique et une valeur de données associée.  
  
## Syntaxe  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<pair <const Key, Type> >   
>  
class hash_multimap  
```  
  
#### Paramètres  
 `Key`  
 Type de données de la clé à stocker dans l'objet hash\_multimap.  
  
 `Type`  
 Type de données de l'élément à stocker dans l'objet hash\_multimap.  
  
 `Traits`  
 Type qui inclut les deux objets de fonction, une de la classe `Traits` capable de comparer deux valeurs d'éléments comme clés de tri pour déterminer leur ordre relatif, et une fonction de hachage qui est un prédicat unaire qui mappe les valeurs de clé des éléments à des entiers non signés de type **size\_t**.  Cet argument est facultatif et sa valeur par défaut est `hash_compare``<Key, less<Key> >`.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui encapsule des informations détaillées sur l'allocation et la désallocation de mémoire de la classe hash\_multimap.  Cet argument est facultatif et sa valeur par défaut est `allocator<pair <const Key, Type> >`.  
  
## Notes  
 L'objet hash\_multimap est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  
  
-   Réversible, car elle fournit un itérateur bidirectionnel pour accéder à ses éléments  
  
-   Haché, car ses éléments sont regroupés dans des compartiments selon la valeur d'une fonction de hachage appliquée aux valeurs de clé des éléments.  
  
-   Multiple, car il n'est pas nécessaire que ses éléments possèdent des clés uniques, ce qui permet à une valeur de clé d'être associée à plusieurs valeurs de données d'éléments.  
  
-   Un conteneur associatif de paires, car ses valeurs d'éléments sont distinctes de ses valeurs de clés.  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type de données contenues comme éléments ou comme clés.  Les types de données utilisés pour les éléments et les clés sont eux spécifiés comme paramètres dans la classe de modèle avec la fonction de comparaison et l'allocateur.  
  
 Le principal avantage du hachage sur le tri est une meilleure efficacité : un hachage réussi effectue des insertions, des suppressions et trouve ce qui est recherché dans un délai moyen constant, alors que pour les techniques de tri, ce délai est proportionnel au logarithme du nombre d'éléments du conteneur.  La valeur d'un élément d'une classe hash\_multimap peut être modifiée directement, mais pas la valeur de clé qui y est associée.  Les valeurs de clés associées aux anciens éléments doivent être supprimées, et de nouvelles valeurs de clés doivent être associées aux nouveaux éléments insérés.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs hachés sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces quand elles sont utilisées avec une fonction de hachage bien conçue, car elles les exécutent dans un délai qui est en moyenne constant et ne dépend pas du nombre d'éléments dans le conteneur.  Une fonction de hachage bien conçue produit une distribution uniforme des valeurs de hachage et réduit le nombre de collisions, qui se produisent quand des valeurs de clés distinctes sont mappées dans la même valeur de hachage.  Dans le pire des cas, avec la pire des fonctions de hachage possible, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(délai linéaire\).  
  
 La classe hash\_multimap doit être sélectionnée comme conteneur associatif quand les conditions associant les valeurs à leurs clés sont remplies par l'application.  Pour ce type de structure, il peut s'agir d'une liste triée de mots clés avec des valeurs de chaîne associées fournissant par exemple des définitions, où les mots n'ont pas toujours été définis de manière unique.  Si en revanche, les mots clés ont été définis de façon unique de sorte que les clés sont uniques, il convient d'utiliser un objet hash\_map comme conteneur.  Si en revanche seule la liste des mots doit être stockée, un objet hash\_set est le conteneur correct.  Si plusieurs occurrences d'un mot sont autorisées, un objet hash\_multiset est la structure de conteneur appropriée.  
  
 L'objet hash\_multimap ordonne la séquence qu'il contrôle en appelant un objet `Traits` de hachage stocké de type [value\_compare](../standard-library/value-compare-class.md).  Cet objet stocké est accessible en appelant la fonction membre [key\_comp](../Topic/hash_map::key_comp.md).  Cet objet de fonction doit se comporter comme un objet de la classe [hash\_compare](../standard-library/hash-compare-class.md)`<Key,  less<Key> >`.  En particulier, pour toutes les valeurs `Key` de type `Key`, l'appel `Traits (Key)` génère une distribution des valeurs de type `size_t`.  
  
 En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Ceci entraîne un ordonnancement entre les éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire f\(x,y\) est un objet de fonction qui a deux objets d'argument `x` et `y`, et une valeur de retour `true` ou `false`.  Un tri appliqué à un objet hash\_multimap est un ordre faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive, où deux objets `x` et `y` sont définis comme équivalents quand f\(x, y\) et f\(y, x\) ont la valeur `false`.  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction d'ordonnancement et de la taille actuelle de la table de hachage stockée dans l'objet conteneur.  Vous ne pouvez pas déterminer la taille actuelle de la table de hachage, et vous ne pouvez donc généralement pas prédire l'ordre des éléments dans la séquence contrôlée.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 L'itérateur fourni par la classe hash\_multimap est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/hash_multimap::insert.md) et [hash\_multimap](../Topic/hash_multimap::hash_multimap.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications des fonctionnalités sont inférieures à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur a son propre hash\_multimap de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un hash\_multimap minimal de fonctionnalités, mais il est suffisant pour pouvoir parler de plage d'itérateurs `[First, Last)` dans le contexte des fonctions membres.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l'espace de noms std. Ils ont été transférés dans l'espace de noms stdext.  Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[hash\_multimap](../Topic/hash_multimap::hash_multimap.md)|Construit une liste d'une taille spécifique ou avec des éléments d'une valeur spécifique ou avec un `allocator` spécifique, ou comme copie d'un autre objet `hash_multimap`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_multimap::allocator_type.md)|Type qui représente la classe `allocator` pour l'objet `hash_multimap`.|  
|[const\_iterator](../Topic/hash_multimap::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans le `hash_multimap`.|  
|[const\_pointer](../Topic/hash_multimap::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un `hash_multimap`.|  
|[const\_reference](../Topic/hash_multimap::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans un `hash_multimap` pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/hash_multimap::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans le `hash_multimap`.|  
|[difference\_type](../Topic/hash_multimap::difference_type.md)|Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'un `hash_multimap` au sein d'une plage, parmi les éléments pointés par les itérateurs.|  
|[iterator](../Topic/hash_multimap::iterator.md)|Type qui fournit un itérateur bidirectionnel, qui peut lire ou modifier tout élément d'un objet `hash_multimap`.|  
|[key\_compare](../Topic/hash_multimap::key_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments au sein d'un `hash_multimap`.|  
|[key\_type](../Topic/hash_multimap::key_type.md)|Type qui décrit l'objet de clé de tri qui constitue chaque élément du `hash_multimap`.|  
|[mapped\_type](../Topic/hash_multimap::mapped_type.md)|Type qui représente le type de données stocké dans un `hash_multimap`.|  
|[pointer](../Topic/hash_multimap::pointer.md)|Type qui fournit un pointeur vers un élément d'un objet `hash_multimap`.|  
|[référence](../Topic/hash_multimap::reference.md)|Type qui fournit une référence à un élément stocké dans un `hash_multimap`.|  
|[reverse\_iterator](../Topic/hash_multimap::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'un `hash_multimap` inversé.|  
|[type\_taille](../Topic/hash_multimap::size_type.md)|Type entier non signé qui peut représenter le nombre d'éléments dans un `hash_multimap`.|  
|[value\_type](../Topic/hash_multimap::value_type.md)|Type qui fournit un objet de fonction pouvant comparer deux éléments comme clés de tri pour déterminer leur ordre relatif dans le `hash_multimap`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/hash_multimap::begin.md)|Retourne un itérateur traitant le premier élément d'un `hash_multimap`.|  
|[hash\_multimap::cbegin](../Topic/hash_multimap::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_multimap`.|  
|[hash\_multimap::cend](../Topic/hash_multimap::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'un `hash_multimap`.|  
|[effacer](../Topic/hash_multimap::clear.md)|Efface tous les éléments d'un `hash_multimap`.|  
|[count](../Topic/hash_multimap::count.md)|Retourne le nombre d'éléments d'un `hash_multimap` dont la clé correspond à une clé spécifiée par un paramètre.|  
|[hash\_multimap::crbegin](../Topic/hash_multimap::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_multimap` inversé.|  
|[hash\_multimap::crend](../Topic/hash_multimap::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un `hash_multimap` inversé.|  
|[hash\_multimap::emplace](../Topic/hash_multimap::emplace.md)|Insère un élément construit sur place dans un `hash_multimap`.|  
|[hash\_multimap::emplace\_hint](../Topic/hash_multimap::emplace_hint.md)|Insère un élément construit sur place dans un `hash_multimap`, avec un indicateur de positionnement.|  
|[vide](../Topic/hash_multimap::empty.md)|Vérifie si un `hash_multimap` est vide.|  
|[end](../Topic/hash_multimap::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_multimap`.|  
|[equal\_range](../Topic/hash_multimap::equal_range.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_multimap`.|  
|[erase](../Topic/hash_multimap::erase.md)|Supprime un élément ou une plage d'éléments aux positions spécifiées d'un objet `hash_multimap`.|  
|[find](../Topic/hash_multimap::find.md)|Retourne un itérateur qui référence l'emplacement d'un élément d'un objet `hash_multimap` qui a une clé équivalente à une clé spécifiée.|  
|[get\_allocator](../Topic/hash_multimap::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire le `hash_multimap`.|  
|[insérer](../Topic/hash_multimap::insert.md)|Insère un élément ou une plage d'éléments dans l'objet `hash_multimap` à un emplacement spécifié.|  
|[key\_comp](../Topic/hash_multimap::key_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les clés au sein d'un `hash_multimap`.|  
|[lower\_bound](../Topic/hash_multimap::lower_bound.md)|Retourne un itérateur pointant vers le premier élément d'un objet `hash_multimap` qui a une valeur de clé supérieure ou égale à celle d'une clé spécifiée.|  
|[max\_size](../Topic/hash_multimap::max_size.md)|Retourne la longueur maximale du `hash_multimap`.|  
|[rbegin](../Topic/hash_multimap::rbegin.md)|Retourne un itérateur qui traite le premier élément d'un `hash_multimap` inversé.|  
|[rend](../Topic/hash_multimap::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_multimap` inversé.|  
|[size](../Topic/hash_multimap::size.md)|Spécifie une nouvelle taille pour un objet `hash_multimap`.|  
|[échange](../Topic/hash_multimap::swap.md)|Échange les éléments de deux `hash_multimap`.|  
|[upper\_bound](../Topic/hash_multimap::upper_bound.md)|Retourne un itérateur pointant vers le premier élément d'un objet `hash_multimap` qui a une valeur de clé supérieure à celle d'une clé spécifiée.|  
|[value\_comp](../Topic/hash_multimap::value_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour ordonner les valeurs des éléments d'un objet `hash_multimap`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[hash\_multimap::operator\=](../Topic/hash_multimap::operator=.md)|Remplace les éléments d'un `hash_multimap` par une copie d'un autre `hash_multimap`.|  
  
## Configuration requise  
 **En\-tête :** \<hash\_map\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)