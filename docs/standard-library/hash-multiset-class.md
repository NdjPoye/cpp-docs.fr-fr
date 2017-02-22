---
title: "hash_multiset, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.hash_multiset"
  - "std::hash_multiset"
  - "stdext::hash_multiset"
  - "hash_multiset"
  - "std.hash_multiset"
  - "hash_set/stdext::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multiset (classe)"
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# hash_multiset, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette API méthode est obsolète.  L'alternative est [unordered\_multiset, classe](../standard-library/unordered-multiset-class.md).  
  
 La classe conteneur hash\_multiset est une extension de STL, et elle est utilisée pour le stockage et la récupération rapide des données d'une collection dans laquelle les valeurs des éléments contenus servent de valeurs de clés et ne doivent pas être uniques.  
  
## Syntaxe  
  
```  
  
        template <  
   class Key,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<Key>   
>  
class hash_multiset  
```  
  
#### Paramètres  
 *Clé*  
 Type de données de l'élément à stocker dans le hash\_multiset.  
  
 `Traits`  
 Type qui inclut les deux objets de fonction, une de comparaison de classes qui est un prédicat binaire capable de comparer deux valeurs d'éléments comme clés de tri pour déterminer leur ordre relatif, et une fonction de hachage qui est un prédicat unaire qui mappe les valeurs de clé des éléments à des entiers non signés de type **size\_t**.  Cet argument est facultatif et le prédicat `hash_compare`*\<Key,* **less***\<Key\> \>* est la valeur par défaut.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui encapsule des informations sur l'allocation et la désallocation de mémoire du hash\_multiset.  Cet argument est facultatif et sa valeur par défaut est **allocator***\<Key\>.*  
  
## Notes  
 Le hash\_multiset est :  
  
-   Un conteneur associatif de taille variable qui prend en charge la récupération efficace des valeurs d'éléments selon une valeur de clé associée.  C'est également un conteneur associatif simple, car les valeurs de ses éléments sont ses valeurs de clés.  
  
-   Réversible, car elle fournit un itérateur bidirectionnel pour accéder à ses éléments  
  
-   Haché, car ses éléments sont regroupés dans des compartiments selon la valeur d'une fonction de hachage appliquée aux valeurs de clé des éléments.  
  
-   Unique dans le sens où chacun de ses éléments doit avoir une clé unique.  Comme hash\_multiset est également un simple conteneur associatif, ses éléments sont également uniques.  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et donc indépendante du type spécifique des données contenues comme éléments ou comme clés.  Les types de données utilisés pour les éléments et les clés sont eux spécifiés comme paramètres dans la classe de modèle avec la fonction de comparaison et l'allocateur.  
  
 Le principal avantage du hachage sur le tri est une meilleure efficacité : un hachage réussi effectue des insertions, des suppressions et trouve ce qui est recherché dans un délai moyen constant, alors que pour les techniques de tri, ce délai est proportionnel au logarithme du nombre d'éléments du conteneur.  La valeur d'un élément appartenant à une classe set ne peut pas être modifiée directement.  Vous devez supprimer les anciennes valeurs et insérer les éléments ayant de nouvelles valeurs.  
  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application.  Les conteneurs associatifs hachés sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations sont efficaces quand elles sont utilisées avec une fonction de hachage bien conçue, car elles les exécutent dans un délai qui est en moyenne constant et ne dépend pas du nombre d'éléments dans le conteneur.  Une fonction de hachage bien conçue produit une distribution uniforme des valeurs de hachage et réduit le nombre de collisions, qui se produisent quand des valeurs de clés distinctes sont mappées dans la même valeur de hachage.  Dans le pire des cas, avec la pire des fonctions de hachage possible, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence \(délai linéaire\).  
  
 Le hash\_multiset doit être sélectionné comme conteneur associatif quand les conditions associant les valeurs à leurs clés sont remplies par l'application.  Les éléments d'un hash\_multiset peuvent être nombreux et être utilisés comme leurs propres clés de tri : les clés ne sont donc pas uniques.  Pour ce type de structure, il peut s'agir d'une liste triée de mots qui peuvent apparaître plusieurs fois.  Si les occurrences multiples de mots ne sont pas autorisées, c'est un hash\_set qu'il convient d'utiliser comme structure de conteneur.  Si des définitions uniques sont jointes comme valeurs à la liste de mots clés uniques, c'est un hash\_map qu'il convient d'utiliser comme structure pour contenir ces données.  Si les définitions ne sont pas uniques, c'est un hash\_multimap qu'il convient d'utiliser comme conteneur.  
  
 Le hash\_multiset ordonne la séquence qu'il contrôle en appelant un objet de caractéristiques de hachage stocké de type [value\_compare](../Topic/hash_multiset::value_compare.md).  Cet objet stocké est accessible en appelant la fonction membre [key\_comp](../Topic/hash_multiset::key_comp.md).  Cet objet de fonction doit se comporter comme un objet de classe `hash_compare`*\<Key,* **less***\<Key\> \>*. En particulier, pour toutes les valeurs *Key* de type **Key**, l'appel **Trait**\(*Key*\) génère une distribution des valeurs de type **size\_t**.  
  
 En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\), soit que l'un est inférieur à l'autre.  Cela entraîne le tri des éléments non équivalents.  D'un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  Un prédicat binaire *f*\(*x*,*y*\) est un objet de fonction qui a deux objets arguments x et y, et une valeur de retour true ou false.  Un tri appliqué à un hash\_multiset est un ordonnancement faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive, où deux objets x et y sont définis comme équivalents quand *f*\(*x*,*y*\) et *f*\(*y*,*x*\) ont toutes deux la valeur false.  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction d'ordonnancement et de la taille actuelle de la table de hachage stockée dans l'objet conteneur.  Vous ne pouvez pas déterminer la taille actuelle de la table de hachage, et vous ne pouvez donc généralement pas prédire l'ordre des éléments dans la séquence contrôlée.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 L'itérateur fourni par la classe hash\_multiset est un itérateur bidirectionnel. Toutefois, les fonctions membres de classe [insert](../Topic/set::insert.md) et [hash\_multiset](../Topic/set::set.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications des fonctionnalités sont inférieures à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs forment une famille liée par les améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre hash\_multiset de spécifications, et les algorithmes qui fonctionnent avec eux doivent limiter leurs hypothèses aux spécifications fournies par ce type d'itérateur.  On peut considérer qu'un itérateur d'entrée peut être déréférencé pour faire référence à un objet et qu'il peut être incrémenté à l'itérateur suivant dans la séquence.  Il s'agit d'un hash\_multiset minimal de fonctionnalités, mais il est suffisant pour pouvoir parler de plage d'itérateurs \[`_First`, `_Last`\) dans le contexte des fonctions membres de la classe.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l'espace de noms std. Ils ont été transférés dans l'espace de noms stdext.  Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[hash\_multiset](../Topic/hash_multiset::hash_multiset.md)|Construit un `hash_multiset` vide ou une copie de l'ensemble ou d'une partie d'un autre `hash_multiset`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_multiset::allocator_type.md)|Type qui représente la classe `allocator` pour l'objet `hash_multiset`.|  
|[const\_iterator](../Topic/hash_multiset::const_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans le `hash_multiset`.|  
|[const\_pointer](../Topic/hash_multiset::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un `hash_multiset`.|  
|[const\_reference](../Topic/hash_multiset::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans un `hash_multiset` pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/hash_multiset::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans le `hash_multiset`.|  
|[difference\_type](../Topic/hash_multiset::difference_type.md)|Type entier signé qui fournit la différence entre deux itérateurs qui font référence à des éléments d'un même objet `hash_multiset`.|  
|[iterator](../Topic/hash_multiset::iterator.md)|Type qui fournit un itérateur bidirectionnel, qui peut lire ou modifier tout élément d'un objet `hash_multiset`.|  
|[key\_compare](../Topic/hash_multiset::key_compare.md)|Type qui fournit un objet de fonction pouvant comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments au sein d'un `hash_multiset`.|  
|[key\_type](../Topic/hash_multiset::key_type.md)|Type qui décrit un objet stocké comme élément d'un objet `hash_set` dans sa capacité comme clé de tri.|  
|[pointer](../Topic/hash_multiset::pointer.md)|Type qui fournit un pointeur vers un élément d'un objet `hash_multiset`.|  
|[référence](../Topic/hash_multiset::reference.md)|Type qui fournit une référence à un élément stocké dans un `hash_multiset`.|  
|[reverse\_iterator](../Topic/hash_multiset::reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire ou de modifier tout élément d'un `hash_multiset` inversé.|  
|[type\_taille](../Topic/hash_multiset::size_type.md)|Type entier non signé qui peut représenter le nombre d'éléments dans un `hash_multiset`.|  
|[value\_compare](../Topic/hash_multiset::value_compare.md)|Type qui fournit deux objets de fonction, un prédicat binaire de la comparaison de classe qui peut comparer deux valeurs d'éléments d'un `hash_multiset` pour déterminer leur ordre relatif et un prédicat unaire qui hache les éléments.|  
|[value\_type](../Topic/hash_multiset::value_type.md)|Type qui décrit un objet stocké comme élément d'un objet `hash_multiset` dans sa capacité comme valeur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/hash_multiset::begin.md)|Retourne un itérateur qui référence le premier élément d'un objet `hash_multiset`.|  
|[hash\_multiset::cbegin](../Topic/hash_multiset::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_multiset`.|  
|[hash\_multiset::cend](../Topic/hash_multiset::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'un `hash_multiset`.|  
|[effacer](../Topic/hash_multiset::clear.md)|Efface tous les éléments d'un `hash_multiset`.|  
|[count](../Topic/hash_multiset::count.md)|Retourne le nombre d'éléments d'un objet `hash_multiset` dont la clé correspond à une clé spécifiée par un paramètre.|  
|[hash\_multiset::crbegin](../Topic/hash_multiset::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'un `hash_multiset` inversé.|  
|[hash\_multiset::crend](../Topic/hash_multiset::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un `hash_multiset` inversé.|  
|[hash\_multiset::emplace](../Topic/hash_multiset::emplace.md)|Insère un élément construit sur place dans un `hash_multiset`.|  
|[hash\_multiset::emplace\_hint](../Topic/hash_multiset::emplace_hint.md)|Insère un élément construit sur place dans un `hash_multiset`, avec un indicateur de positionnement.|  
|[vide](../Topic/hash_multiset::empty.md)|Vérifie si un `hash_multiset` est vide.|  
|[end](../Topic/hash_multiset::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_multiset`.|  
|[equal\_range](../Topic/hash_multiset::equal_range.md)|Retourne une paire d'itérateurs, respectivement vers le premier élément d'un objet `hash_multiset` avec une clé supérieure à une clé spécifiée, et vers le premier élément d'un objet `hash_multiset` avec une clé supérieure ou égale à la clé.|  
|[erase](../Topic/hash_multiset::erase.md)|Supprime d'un emplacement spécifié un élément ou une plage d'éléments compris dans un `hash_multiset` ou supprime les éléments qui correspondent à une clé spécifiée.|  
|[find](../Topic/hash_multiset::find.md)|Retourne un itérateur qui référence l'emplacement d'un élément d'un objet `hash_multiset` qui a une clé équivalente à une clé spécifiée.|  
|[get\_allocator](../Topic/hash_multiset::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire le `hash_multiset`.|  
|[insérer](../Topic/hash_multiset::insert.md)|Insère un élément ou une plage d'éléments dans un `hash_multiset`.|  
|[key\_comp](../Topic/hash_multiset::key_compare.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les clés au sein d'un `hash_multiset`.|  
|[lower\_bound](../Topic/hash_multiset::lower_bound.md)|Retourne un itérateur au premier élément d'un `hash_multiset` avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[max\_size](../Topic/hash_multiset::max_size.md)|Retourne la longueur maximale du `hash_multiset`.|  
|[rbegin](../Topic/hash_multiset::rbegin.md)|Retourne un itérateur qui traite le premier élément d'un `hash_multiset` inversé.|  
|[rend](../Topic/hash_multiset::rend.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un `hash_multiset` inversé.|  
|[size](../Topic/hash_multiset::size.md)|Retourne le nombre d'éléments d'un `hash_multiset`.|  
|[échange](../Topic/hash_multiset::swap.md)|Échange les éléments de deux `hash_multiset`.|  
|[upper\_bound](../Topic/hash_multiset::upper_bound.md)|Retourne un itérateur au premier élément d'un `hash_multiset` avec une valeur de clé supérieure ou égale à celle de la clé spécifiée.|  
|[value\_comp](../Topic/hash_multiset::value_comp.md)|Récupère une copie de l'objet de caractéristiques de hachage utilisé pour hacher et ordonner les valeurs des clés d'éléments dans un objet `hash_multiset`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[hash\_multiset::operator\=](../Topic/hash_multiset::operator=.md)|Remplace les éléments du  par une copie d'un autre .|  
  
## Configuration requise  
 **En\-tête :** \<hash\_set\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)