---
title: "hash_set, classe | Microsoft Docs"
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
  - "hash_set/stdext::hash_set"
  - "std::hash_set"
  - "std.hash_set"
  - "stdext::hash_set"
  - "hash_set"
  - "stdext.hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set (classe)"
ms.assetid: c765c06e-cbb6-48c2-93ca-d15468eb28d7
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash_set, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette API méthode est obsolète.  L'alternative est [unordered\_set, classe](../standard-library/unordered-set-class.md).  
  
 La classe conteneur hash\_set est une extension de STL, et elle est utilisée pour le stockage et la récupération rapide des données d'une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.  
  
## Syntaxe  
  
```  
template <  
   class Key,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<Key>   
>  
class hash_set  
```  
  
#### Paramètres  
 `Key`  
 Type de données de l'élément à stocker dans l'objet hash\_set.  
  
 `Traits`  
 Type qui inclut les deux objets de fonction, une de comparaison de classes qui est un prédicat binaire capable de comparer deux valeurs d'éléments comme clés de tri pour déterminer leur ordre relatif, et une fonction de hachage qui est un prédicat unaire qui mappe les valeurs de clé des éléments à des entiers non signés de type **size\_t**.  Cet argument est facultatif et le prédicat `hash_compare`*\<Key,* **less***\<Key\> \>* est la valeur par défaut.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire de la classe hash\_set.  Cet argument est facultatif et sa valeur par défaut est **allocator***\<Key\>.*  
  
## Notes  
 L'objet hash\_set est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  C'est également un conteneur associatif simple, car les valeurs de ses éléments sont ses valeurs de clés.  
  
-   Réversible, car elle fournit un itérateur bidirectionnel pour accéder à ses éléments  
  
-   Haché, car ses éléments sont regroupés dans des compartiments selon la valeur d'une fonction de hachage appliquée aux valeurs de clé des éléments.  
  
-   Unique dans le sens où chacun de ses éléments doit avoir une clé unique.  Comme hash\_set est également un simple conteneur associatif, ses éléments sont également uniques.  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type spécifique des données contenues comme éléments ou comme clés.  Les types de données utilisés pour les éléments et les clés sont eux spécifiés comme paramètres dans la classe de modèle avec la fonction de comparaison et l'allocateur.  
  
 Le principal avantage du hachage sur le tri est une meilleure efficacité : un hachage réussi effectue des insertions, des suppressions et trouve ce qui est recherché dans un délai moyen constant, alors que pour les techniques de tri, ce délai est proportionnel au logarithme du nombre d'éléments du conteneur.  La valeur d'un élément appartenant à une classe set ne peut pas être modifiée directement.  Vous devez supprimer les anciennes valeurs et insérer les éléments ayant de nouvelles valeurs.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs hachés sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces quand elles sont utilisées avec une fonction de hachage bien conçue, car elles les exécutent dans un délai qui est en moyenne constant et ne dépend pas du nombre d'éléments dans le conteneur.  Une fonction de hachage bien conçue produit une distribution uniforme des valeurs de hachage et réduit le nombre de collisions, qui se produisent quand des valeurs de clés distinctes sont mappées dans la même valeur de hachage.  Dans le pire des cas, avec la pire des fonctions de hachage possible, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(délai linéaire\).  
  
 La classe hash\_set doit être sélectionnée comme conteneur associatif lorsque les conditions associant les valeurs à leurs clés sont remplies par l'application.  Les éléments d'une classe hash\_set sont uniques et agissent comme leurs propres clés de tri.  Pour ce type de structure, il peut s'agir d'une liste triée de mots qui ne peuvent apparaître qu'une seule fois.  Si plusieurs occurrences d'un mot sont autorisées, un objet hash\_multiset est la structure de conteneur appropriée.  Si les valeurs doivent être jointes à une liste de mots clés uniques, il convient d'utiliser une classe hash\_map comme conteneur de données.  Si les clés ne sont pas uniques, c'est une classe hash\_multimap qu'il convient d'utiliser comme conteneur.  
  
 L'objet hash\_set ordonne la séquence qu'il contrôle en appelant un objet **Traits** de hachage stocké de type [value\_compare](../Topic/hash_set::value_compare.md).  Cet objet stocké est accessible en appelant la fonction membre [key\_comp](../Topic/hash_set::key_comp.md).  Cet objet de fonction doit se comporter comme un objet de la classe *hash\_compare\<Key, less\<Key\> \>.* En particulier, pour toutes les valeurs `_Key` de type Key, l'appel Trait\(`_Key`\) génère une distribution des valeurs de type size\_t.  
  
 En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Ceci entraîne un ordonnancement entre les éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire *f*\(*x*,*y*\) est un objet de fonction qui a deux objets arguments x et y, et une valeur de retour true ou false.  Un tri appliqué à un objet hash\_set est un ordonnancement faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive \(où deux objets *x* et *y* sont définis comme équivalents quand *f*\(*x*,*y*\) and *f*\(*y*,*x*\) ont la valeur false\).  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction d'ordonnancement et de la taille actuelle de la table de hachage stockée dans l'objet conteneur.  Vous ne pouvez pas déterminer la taille actuelle de la table de hachage, et vous ne pouvez donc généralement pas prédire l'ordre des éléments dans la séquence contrôlée.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 L'itérateur fourni par la classe hash\_set est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/hash_set::insert.md) et [hash\_set](../Topic/hash_set::hash_set.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications de fonctionnalités sont minimales par rapport à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre ensemble de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un ensemble minimal de fonctionnalités, mais c'est suffisant pour pouvoir parler d'une plage d'itérateurs \[`_First`, `_Last`\) dans le contexte des fonctions membres de la classe.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l'espace de noms std. Ils ont été transférés dans l'espace de noms stdext.  Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[hash\_set](../Topic/hash_set::hash_set.md)|Construit un `hash_set` vide ou une copie de l'ensemble ou d'une partie d'un autre `hash_set`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_set::allocator_type.md)|Type qui représente la classe `allocator` pour l'objet `hash_set`.|  
|[const\_iterator](../Topic/hash_set::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans le `hash_set`.|  
|[const\_pointer](../Topic/hash_set::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un `hash_set`.|  
|[const\_reference](../Topic/hash_set::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans un `hash_set` pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/hash_set::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans le `hash_set`.|  
|[difference\_type](../Topic/hash_set::difference_type.md)|Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'un `hash_set` au sein d'une plage, parmi les éléments pointés par les itérateurs.|  
|[iterator](../Topic/hash_set::iterator.md)|Type qui fournit un itérateur bidirectionnel, qui peut lire ou modifier tout élément d'un objet `hash_set`.|  
|[key\_compare](../Topic/hash_set::key_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments au sein d'un `hash_set`.|  
|[key\_type](../Topic/hash_set::key_type.md)|Type qui décrit un objet stocké comme élément d'un objet `hash_set` dans sa capacité comme clé de tri.|  
|[pointer](../Topic/hash_set::pointer.md)|Type qui fournit un pointeur vers un élément d'un objet `hash_set`.|  
|[référence](../Topic/hash_set::reference.md)|Type qui fournit une référence à un élément stocké dans un `hash_set`.|  
|[reverse\_iterator](../Topic/hash_set::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'un `hash_set` inversé.|  
|[type\_taille](../Topic/hash_set::size_type.md)|Type entier non signé qui peut représenter le nombre d'éléments dans un `hash_set`.|  
|[value\_compare](../Topic/hash_set::value_compare.md)|Type qui fournit deux objets de fonction, un prédicat binaire de la comparaison de classe qui peut comparer deux valeurs d'éléments d'un `hash_set` pour déterminer leur ordre relatif et un prédicat unaire qui hache les éléments.|  
|[value\_type](../Topic/hash_set::value_type.md)|Type qui décrit un objet stocké comme élément d'un objet `hash_set` dans sa capacité comme valeur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/hash_set::begin.md)|Retourne un itérateur qui référence le premier élément d'un objet `hash_set`.|  
|[hash\_set::cbegin](../Topic/hash_set::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_set`.|  
|[hash\_set::cend](../Topic/hash_set::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'un `hash_set`.|  
|[effacer](../Topic/hash_set::clear.md)|Efface tous les éléments d'un `hash_set`.|  
|[count](../Topic/hash_set::count.md)|Retourne le nombre d'éléments d'un `hash_set` dont la clé correspond à une clé spécifiée par un paramètre.|  
|[hash\_set::crbegin](../Topic/hash_set::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_set` inversé.|  
|[hash\_set::crend](../Topic/hash_set::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un `hash_set` inversé.|  
|[hash\_set::emplace](../Topic/hash_set::emplace.md)|Insère un élément construit sur place dans un `hash_set`.|  
|[hash\_set::emplace\_hint](../Topic/hash_set::emplace_hint.md)|Insère un élément construit sur place dans un `hash_set`, avec un indicateur de positionnement.|  
|[vide](../Topic/hash_set::empty.md)|Vérifie si un `hash_set` est vide.|  
|[end](../Topic/hash_set::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_set`.|  
|[equal\_range](../Topic/hash_set::equal_range.md)|Retourne une paire d'itérateurs, respectivement vers le premier élément d'un objet `hash_set` avec une clé supérieure à une clé spécifiée, et vers le premier élément d'un objet `hash_set` avec une clé supérieure ou égale à la clé.|  
|[erase](../Topic/hash_set::erase.md)|Supprime d'un emplacement spécifié un élément ou une plage d'éléments compris dans un `hash_set` ou supprime les éléments qui correspondent à une clé spécifiée.|  
|[find](../Topic/hash_set::find.md)|Retourne un itérateur qui référence l'emplacement d'un élément d'un objet `hash_set` qui a une clé équivalente à une clé spécifiée.|  
|[get\_allocator](../Topic/hash_set::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire le `hash_set`.|  
|[insérer](../Topic/hash_set::insert.md)|Insère un élément ou une plage d'éléments dans un `hash_set`.|  
|[key\_comp](../Topic/hash_set::key_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les clés au sein d'un `hash_set`.|  
|[lower\_bound](../Topic/hash_set::lower_bound.md)|Retourne un itérateur au premier élément d'un `hash_set` avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[max\_size](../Topic/hash_set::max_size.md)|Retourne la longueur maximale du `hash_set`.|  
|[rbegin](../Topic/hash_set::rbegin.md)|Retourne un itérateur qui traite le premier élément d'un `hash_set` inversé.|  
|[rend](../Topic/hash_set::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_set` inversé.|  
|[size](../Topic/hash_set::size.md)|Retourne le nombre d'éléments d'un `hash_set`.|  
|[échange](../Topic/hash_set::swap.md)|Échange les éléments de deux `hash_set`.|  
|[upper\_bound](../Topic/hash_set::upper_bound.md)|Retourne un itérateur au premier élément d'un `hash_set` avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[value\_comp](../Topic/hash_set::value_comp.md)|Récupère une copie de l'objet de caractéristiques de hachage utilisé pour hacher et ordonner les valeurs des clés d'éléments dans un objet `hash_set`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[hash\_set::operator\=](../Topic/hash_set::operator=.md)|Remplace les éléments d'un `hash_set` par une copie d'un autre `hash_set`.|  
  
## Configuration requise  
 **En\-tête :** \<hash\_set\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)