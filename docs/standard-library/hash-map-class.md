---
title: "hash_map, classe | Microsoft Docs"
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
  - "stdext::hash_map"
  - "hash_map/stdext::hash_map"
  - "std.hash_map"
  - "stdext.hash_map"
  - "std::hash_map"
  - "hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map (classe)"
ms.assetid: 40879dfc-51ba-4a59-9f9e-26208de568a8
caps.latest.revision: 25
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash_map, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette API méthode est obsolète.  L'alternative est [unordered\_map, classe](../standard-library/unordered-map-class.md).  
  
 Stocke et récupère des données rapidement auprès d'une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur est unique et une valeur de données associée.  
  
## Syntaxe  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<pair <const Key, Type> >   
>  
class hash_map  
```  
  
#### Paramètres  
 `Key`  
 Type de données de la clé à stocker dans l'objet hash\_map.  
  
 `Type`  
 Type de données de l'élément à stocker dans l'objet hash\_map.  
  
 `Traits`  
 Type qui inclut les deux objets de fonction, une de comparaison de classes capable de comparer deux valeurs d'éléments comme clés de tri pour déterminer leur ordre relatif, et une fonction de hachage qui est un prédicat unaire qui mappe les valeurs de clé des éléments à des entiers non signés de type `size_t`.  Cet argument est facultatif et le prédicat hash\_compare\<`Key`, less\<`Key`\> \> est la valeur par défaut.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui encapsule des informations détaillées sur l'allocation et la désallocation de mémoire de la classe hash\_map.  Cet argument est facultatif et la valeur par défaut est allocator\<pair \<const `Key`, `Type`\>\>.  
  
## Notes  
 L'objet hash\_map est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  
  
-   Réversible, car elle fournit un itérateur bidirectionnel pour accéder à ses éléments  
  
-   Haché, car ses éléments sont regroupés dans des compartiments selon la valeur d'une fonction de hachage appliquée aux valeurs de clé des éléments.  
  
-   Unique dans le sens où chacun de ses éléments doit avoir une clé unique.  
  
-   Un conteneur associatif de paires, car ses valeurs de données d'éléments sont séparées de ses valeurs de clés.  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type de données contenues comme éléments ou comme clés.  Les types de données utilisés pour les éléments et les clés sont eux spécifiés comme paramètres dans la classe de modèle avec la fonction de comparaison et l'allocateur.  
  
 Le principal avantage du hachage sur le tri est une meilleure efficacité : un hachage réussi effectue des insertions, des suppressions et trouve ce qui est recherché dans un délai moyen constant, alors que pour les techniques de tri, ce délai est proportionnel au logarithme du nombre d'éléments du conteneur.  La valeur d'un élément d'un objet hash\_map peut être modifiée directement, mais pas la valeur de la clé qui y est associée.  Les valeurs de clés associées aux anciens éléments doivent être supprimées, et de nouvelles valeurs de clés doivent être associées aux nouveaux éléments insérés.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs hachés sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces quand elles sont utilisées avec une fonction de hachage bien conçue, car elles les exécutent dans un délai qui est en moyenne constant et ne dépend pas du nombre d'éléments dans le conteneur.  Une fonction de hachage bien conçue produit une distribution uniforme des valeurs de hachage et réduit le nombre de collisions, qui se produisent quand des valeurs de clés distinctes sont mappées dans la même valeur de hachage.  Dans le pire des cas, avec la pire des fonctions de hachage possible, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(délai linéaire\).  
  
 L'objet hash\_map doit être sélectionné comme conteneur associatif quand les conditions associant les valeurs à leurs clés sont remplies par l'application.  Un modèle pour ce type de structure est une liste ordonnée de mots clés uniques avec des valeurs de chaîne associées qui fournissent par exemple des définitions.  Si au lieu de cela, un mot a plusieurs définitions correctes, de sorte que les clés ne sont pas uniques, il convient de choisir un objet hash\_multimap comme conteneur.  Si en revanche seule la liste des mots doit être stockée, un objet hash\_set est le conteneur correct.  Si plusieurs occurrences d'un mot sont autorisées, un objet hash\_multiset est la structure de conteneur appropriée.  
  
 L'objet hash\_multiset ordonne la séquence qu'il contrôle en appelant un objet `Traits` de hachage stocké de la classe [value\_compare](../standard-library/value-compare-class.md).  Cet objet stocké est accessible en appelant la fonction membre [key\_comp](../Topic/hash_map::key_comp.md).  Cet objet de fonction doit se comporter comme un objet de la classe [hash\_compare](../standard-library/hash-compare-class.md)\<Key, less\<Key\>\>.  En particulier, pour toutes les valeurs `Key` de type `Key`, l'appel `Traits`\(`Key`\) génère une distribution des valeurs de type `size_t`.  
  
 En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Cela entraîne le tri des éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire f\(x,y\) est un objet de fonction qui a deux objets d'argument `x` et `y`, et une valeur de retour `true` ou `false`.  Un ordonnancement appliqué à un objet hash\_map est un ordonnancement faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive \(où deux objets x et y sont définis comme équivalents quand f\(x, y\) et f\(y, x\) ont la valeur false\).  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction d'ordonnancement et de la taille actuelle de la table de hachage stockée dans l'objet conteneur.  Vous ne pouvez pas déterminer la taille actuelle de la table de hachage, et vous ne pouvez donc généralement pas prédire l'ordre des éléments dans la séquence contrôlée.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 L'itérateur fourni par la classe hash\_map est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/hash_map::insert.md) et [hash\_map](../Topic/hash_map::hash_map.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications de fonctionnalités sont minimales par rapport à celles qui sont garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre ensemble de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un ensemble minimal de fonctionnalités, mais c'est suffisant pour pouvoir parler d'une plage d'itérateurs `[First, Last)` dans le contexte des fonctions membres de la classe.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l'espace de noms std. Ils ont été transférés dans l'espace de noms stdext.  Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[hash\_map](../Topic/hash_map::hash_map.md)|Construit un `hash_map` vide ou une copie de l'ensemble ou d'une partie d'un autre `hash_map`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_map::allocator_type.md)|Type qui représente la classe `allocator` pour l'objet `hash_map`.|  
|[const\_iterator](../Topic/hash_map::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans le `hash_map`.|  
|[const\_pointer](../Topic/hash_map::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un `hash_map`.|  
|[const\_reference](../Topic/hash_map::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans un `hash_map` pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/hash_map::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans le `hash_map`.|  
|[difference\_type](../Topic/hash_map::difference_type.md)|Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'un `hash_map` au sein d'une plage, parmi les éléments pointés par les itérateurs.|  
|[iterator](../Topic/hash_map::iterator.md)|Type qui fournit un itérateur bidirectionnel, qui peut lire ou modifier tout élément d'un objet `hash_map`.|  
|[key\_compare](../Topic/hash_map::key_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments au sein d'un `hash_map`.|  
|[key\_type](../Topic/hash_map::key_type.md)|Type qui décrit l'objet de clé de tri qui constitue chaque élément de la classe `hash_map`.|  
|[mapped\_type](../Topic/hash_map::mapped_type.md)|Type qui représente le type de données stocké dans un `hash_map`.|  
|[pointer](../Topic/hash_map::pointer.md)|Type qui fournit un pointeur vers un élément d'un objet `hash_map`.|  
|[référence](../Topic/hash_map::reference.md)|Type qui fournit une référence à un élément stocké dans un `hash_map`.|  
|[reverse\_iterator](../Topic/hash_map::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'un `hash_map` inversé.|  
|[type\_taille](../Topic/hash_map::size_type.md)|Type entier non signé qui peut représenter le nombre d'éléments dans un `hash_map`.|  
|[value\_type](../Topic/hash_map::value_type.md)|Type qui fournit un objet de fonction pouvant comparer deux éléments comme clés de tri pour déterminer leur ordre relatif dans le `hash_map`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[hash\_map::at](../Topic/hash_map::at.md)|Recherche un élément dans un objet `hash_map` avec une valeur de clé spécifiée.|  
|[begin](../Topic/hash_map::begin.md)|Retourne un itérateur traitant le premier élément d'un `hash_map`.|  
|[hash\_map::cbegin](../Topic/hash_map::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_map`.|  
|[hash\_map::cend](../Topic/hash_map::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'un `hash_map`.|  
|[effacer](../Topic/hash_map::clear.md)|Efface tous les éléments d'un `hash_map`.|  
|[count](../Topic/hash_map::count.md)|Retourne le nombre d'éléments d'un `hash_map` dont la clé correspond à une clé spécifiée par un paramètre.|  
|[hash\_map::crbegin](../Topic/hash_map::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_map` inversé.|  
|[hash\_map::crend](../Topic/hash_map::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un `hash_map` inversé.|  
|[hash\_map::emplace](../Topic/hash_map::emplace.md)|Insère un élément construit sur place dans un `hash_map`.|  
|[hash\_map::emplace\_hint](../Topic/hash_map::emplace_hint.md)|Insère un élément construit sur place dans un `hash_map`, avec un indicateur de positionnement.|  
|[vide](../Topic/hash_map::empty.md)|Vérifie si un `hash_map` est vide.|  
|[end](../Topic/hash_map::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_map`.|  
|[equal\_range](../Topic/hash_map::equal_range.md)|Retourne une paire d'itérateurs, respectivement vers le premier élément d'un objet `hash_map` avec une clé supérieure à une clé spécifiée, et vers le premier élément d'un objet `hash_map` avec une clé supérieure ou égale à la clé.|  
|[erase](../Topic/hash_map::erase.md)|Supprime un élément ou une plage d'éléments aux positions spécifiées d'un objet `hash_map`.|  
|[find](../Topic/hash_map::find.md)|Retourne un itérateur qui référence l'emplacement d'un élément d'un objet `hash_map` qui a une clé équivalente à une clé spécifiée.|  
|[get\_allocator](../Topic/hash_map::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire le `hash_map`.|  
|[insérer](../Topic/hash_map::insert.md)|Insère un élément ou une plage d'éléments dans un `hash_map`.|  
|[key\_comp](../Topic/hash_map::key_comp.md)|Retourne un itérateur pointant vers le premier élément d'un objet `hash_map` qui a une valeur de clé supérieure ou égale à celle d'une clé spécifiée.|  
|[lower\_bound](../Topic/hash_map::lower_bound.md)|Retourne un itérateur pointant vers le premier élément d'un objet `hash_map` qui a une valeur de clé supérieure ou égale à celle d'une clé spécifiée.|  
|[max\_size](../Topic/hash_map::max_size.md)|Retourne la longueur maximale du `hash_map`.|  
|[rbegin](../Topic/hash_map::rbegin.md)|Retourne un itérateur qui traite le premier élément d'un `hash_map` inversé.|  
|[rend](../Topic/hash_map::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_map` inversé.|  
|[size](../Topic/hash_map::size.md)|Retourne le nombre d'éléments d'un `hash_map`.|  
|[échange](../Topic/hash_map::swap.md)|Échange les éléments de deux `hash_map`.|  
|[upper\_bound](../Topic/hash_map::upper_bound.md)|Retourne un itérateur pointant vers le premier élément d'un objet `hash_map` qui a une valeur de clé supérieure à celle d'une clé spécifiée.|  
|[value\_comp](../Topic/hash_map::value_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour ordonner les valeurs des éléments d'un objet `hash_map`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator&#91;&#93;](../Topic/hash_map::operator.md)|Insère un élément dans un objet `hash_map` avec une valeur de clé spécifiée.|  
|[hash\_map::operator\=](../Topic/hash_map::operator=.md)|Remplace les éléments d'un `hash_map` par une copie d'un autre `hash_map`.|  
  
## Configuration requise  
 **En\-tête :** \<hash\_map\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)