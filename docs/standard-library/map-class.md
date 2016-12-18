---
title: "map, classe | Microsoft Docs"
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
  - "std::map"
  - "map/std::map"
  - "map"
  - "std.map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map (classe)"
ms.assetid: 7876f4c9-ebb4-4878-af1e-09364c43af0a
caps.latest.revision: 27
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# map, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisé pour le stockage et la récupération de données d'une collection dans laquelle chaque élément est une paire qui a à la fois une valeur de données et une clé de tri.  La valeur de la clé est unique et est utilisée pour trier automatiquement les données.  
  
 La valeur d'un élément dans une classe map peut être modifiée directement.  La valeur de clé est une constante non modifiable.  Les valeurs de clés associées aux anciens éléments doivent être supprimées, et de nouvelles valeurs de clés doivent être insérées pour les nouveaux éléments.  
  
## Syntaxe  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits = less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class map;  
```  
  
#### Paramètres  
 `Key`  
 Type de données clé à stocker dans la classe map.  
  
 `Type`  
 Type de données d'élément à stocker dans la classe map.  
  
 `Traits`  
 Type qui fournit un objet de fonction pouvant comparer deux valeurs d'éléments comme clés de tri afin de déterminer leur ordre relatif dans la classe map.  Cet argument est facultatif et le prédicat binaire `less<``Key``>` est la valeur par défaut.  
  
 Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat std::less\<\> qui n'a aucun paramètre de type.  Pour plus d'informations, consultez [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire de la classe map.  Cet argument est facultatif et sa valeur par défaut est `allocator<pair` `<const``Key`*,* `Type``> >`.  
  
## Notes  
 La classe map STL \(Standard Template Library\) est :  
  
-   Un conteneur de taille variable qui récupère efficacement des valeurs d'éléments selon les valeurs de clés associées  
  
-   Réversible, car elle fournit des itérateurs bidirectionnels pour accéder à ses éléments.  
  
-   Trié, car ses éléments sont classés par valeurs de clés selon une fonction de comparaison spécifiée  
  
-   Unique,  car chacun de ses éléments doit avoir une clé unique.  
  
-   Un conteneur associatif de paires, car ses valeurs de données d'éléments sont séparées de ses valeurs de clés  
  
-   Une classe de modèle, car la fonctionnalité qu'elle fournit est générique et indépendante du type d'élément et du type de clé.  Les types de données utilisés pour des éléments et des clés sont spécifiés comme paramètres dans le modèle de classe avec la fonction de comparaison et l'allocateur.  
  
 L'itérateur fourni par la classe map est un itérateur bidirectionnel, mais les fonctions membres de classe [insert](../Topic/map::insert.md) et [map](../Topic/map::map.md) ont des versions qui prennent comme paramètres de modèle un itérateur d'entrée plus faible, dont les spécifications des fonctionnalités sont moindres par rapport à celles garanties par la classe des itérateurs bidirectionnels.  Les différents concepts d'itérateurs sont liés par des améliorations de leurs fonctionnalités.  Chaque concept d'itérateur possède son propre ensemble de spécifications, et les algorithmes qui fonctionnent avec lui doivent être limités par ces spécifications.  Un itérateur d'entrée peut être déréférencé pour faire référence à un objet et peut être incrémenté à l'itérateur suivant de la séquence.  
  
 Nous vous recommandons de baser le choix du type de conteneur sur le type de recherche et d'insertion qui est requis par l'application.  Les conteneurs associatifs sont optimisés pour les opérations de recherche, d'insertion et de suppression.  Les fonctions membres qui prennent en charge explicitement ces opérations les exécutent en un temps qui est, au pire des cas, proportionnel au logarithme du nombre d'éléments dans le conteneur.  L'insertion d'éléments ne rend aucun itérateur non valide. La suppression d'éléments rend uniquement non valides les itérateurs qui pointaient spécifiquement vers les éléments supprimés.  
  
 Nous vous recommandons de faire de la classe map le conteneur associatif de premier choix lorsque des conditions qui associent des valeurs avec des clés sont remplies par l'application.  Un modèle pour ce type de structure est une liste triée de mots clés à occurrence unique avec des valeurs de chaîne associées qui fournissent des définitions.  Si un mot a plusieurs définitions correctes afin que la clé ne soit pas unique, il convient d'utiliser une classe multimap comme conteneur.  Si seule la liste de mots est stockée, il convient d'utiliser un ensemble comme conteneur.  Si plusieurs occurrences de mots sont autorisées, il convient d'utiliser une classe multiset.  
  
 La classe map trie les éléments qu'elle contrôle en appelant un objet de fonction stocké de type [key\_compare](../Topic/map::key_compare.md).  Cet objet stocké est une fonction de comparaison sollicitée en appelant la méthode [key\_comp](../Topic/map::key_comp.md).  En général, deux éléments donnés sont comparés pour déterminer si l'un est inférieur à l'autre ou s'ils sont équivalents.  Comme tous les éléments sont comparés, une séquence classée d'éléments non équivalents est créée.  
  
> [!NOTE]
>  La fonction de comparaison est un prédicat binaire qui induit un ordre faible strict dans le sens mathématique du terme.  Un prédicat binaire f\(x,y\) est un objet de fonction qui a deux objets d'argument x et y, et une valeur de retour de `true` ou de `false`.  Un tri appliqué à un ensemble est un ordre faible strict si le prédicat binaire est irréflexif, antisymétrique et transitif, et si l'équivalence est transitive, où deux objets x et y sont définis comme équivalents lorsque f\(x,y\) ``  et f\(y,x\) sont `false`.  Si la plus élevée des conditions d'égalité entre les clés remplace celle de l'équivalence, alors le tri devient total \(dans le sens où tous les éléments sont classés les uns par rapport aux autres\), et les clés correspondantes seront alors impossibles à différencier les unes des autres.  
>   
>  Dans C\+\+14, vous pouvez activer la recherche hétérogène en spécifiant le prédicat `std::less<>` ou `std::greater<>` qui n'a aucun paramètre de type.  Pour plus d'informations, consultez [Recherche hétérogène dans les conteneurs associatifs](../standard-library/stl-containers.md#sequence_containers).  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[map](../Topic/map::map.md)|Construit une liste de taille spécifique ou contenant des éléments de valeurs spécifiques, ou contenant un `allocator` spécifique ou comme copie d'une autre classe map.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/map::allocator_type.md)|Typedef pour la classe `allocator` de l'objet map.|  
|[const\_iterator](../Topic/map::const_iterator.md)|Typedef pour un itérateur bidirectionnel qui peut lire un élément `const` dans la classe map.|  
|[const\_pointer](../Topic/map::const_pointer.md)|Typedef pour un pointeur vers un élément `const` d'une classe map.|  
|[const\_reference](../Topic/map::const_reference.md)|Typedef pour une référence à un élément `const` stocké dans une classe map pour lire et effectuer des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/map::const_reverse_iterator.md)|Type qui fournit un itérateur bidirectionnel capable de lire n'importe quel élément `const` dans la classe map.|  
|[difference\_type](../Topic/map::difference_type.md)|Typedef entier signé pour le nombre d'éléments d'une classe map comprise dans une plage d'éléments pointés par des itérateurs.|  
|[iterator](../Topic/map::iterator.md)|Typedef pour un itérateur bidirectionnel qui permet de lire ou de modifier tout élément d'une classe map.|  
|[key\_compare](../Topic/map::key_compare.md)|Typedef pour un objet de fonction qui peut comparer deux clés de tri pour déterminer l'ordre relatif de deux éléments d'une classe map.|  
|[key\_type](../Topic/map::key_type.md)|Typedef pour la clé de tri stockée dans chaque élément de la classe map.|  
|[mapped\_type](../Topic/map::mapped_type.md)|Typedef pour les données stockées dans chaque élément d'une classe map.|  
|[pointer](../Topic/map::pointer.md)|Typedef pour un pointeur vers un élément `const` d'une classe map.|  
|[référence](../Topic/map::reference.md)|Typedef pour une référence à un élément stocké dans une classe map.|  
|[reverse\_iterator](../Topic/map::reverse_iterator.md)|Typedef pour un itérateur bidirectionnel qui permet de lire ou de modifier un élément d'une classe map inversée.|  
|[type\_taille](../Topic/map::size_type.md)|Typedef entier non signé pour le nombre d'éléments d'une classe map.|  
|[value\_type](../Topic/map::value_type.md)|Typedef pour le type d'objet stocké comme élément dans une classe map.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[à](../Topic/map::at.md)|Recherche un élément avec une valeur de clé spécifiée.|  
|[begin](../Topic/map::begin.md)|Retourne un itérateur qui pointe vers le premier élément d'une classe map.|  
|[cbegin](../Topic/map::cbegin.md)|Retourne un itérateur const qui pointe vers le premier élément de la classe map.|  
|[cend](../Topic/map::cend.md)|Retourne un itérateur const de type past\-the\-end.|  
|[effacer](../Topic/map::clear.md)|Efface tous les éléments d'une classe map.|  
|[count](../Topic/map::count.md)|Retourne le nombre d'éléments dans une classe map dont la clé correspond à celle spécifiée dans un paramètre.|  
|[crbegin](../Topic/map::crbegin.md)|Retourne un itérateur const qui pointe vers le premier élément d'une classe map inversée.|  
|[crend](../Topic/map::crend.md)|Retourne un itérateur const qui pointe vers l'emplacement après le dernier élément dans une classe map inversée.|  
|[emplace](../Topic/map::emplace.md)|Insère un élément construit sur place dans la classe map.|  
|[emplace\_hint](../Topic/map::emplace_hint.md)|Insère un élément construit sur place dans la classe map, avec un indicateur de positionnement.|  
|[vide](../Topic/map::empty.md)|Retourne `true` si la classe map est vide.|  
|[end](../Topic/map::end.md)|Retourne l'itérateur past\-the\-end.|  
|[equal\_range](../Topic/map::equal_range.md)|Retourne une paire d'itérateurs.  Le premier itérateur de la paire pointe vers le premier élément d'un `map` avec une clé qui est supérieure à celle spécifiée.  Le deuxième itérateur de la paire pointe vers le premier élément du `map` avec une clé dont la valeur est supérieure ou égale à la clé spécifiée.|  
|[erase](../Topic/map::erase.md)|Supprime un élément ou une plage d'éléments dans une classe map depuis les emplacement spécifiés.|  
|[find](../Topic/map::find.md)|Retourne un itérateur qui indique l'emplacement d'un élément dans une classe map qui a une clé égale à celle spécifiée.|  
|[get\_allocator](../Topic/map::get_allocator.md)|Retourne une copie de l'objet `allocator` qui est utilisé pour construire la classe map.|  
|[insérer](../Topic/map::insert.md)|Insère un élément ou une plage d'éléments dans la classe map à un emplacement spécifié.|  
|[key\_comp](../Topic/map::key_comp.md)|Retourne une copie de l'objet de comparaison utilisé pour trier les clés dans une classe map.|  
|[lower\_bound](../Topic/map::lower_bound.md)|Retourne un itérateur au premier élément d'une classe map qui a une valeur de clé supérieure ou égale à celle d'une clé spécifiée.|  
|[max\_size](../Topic/map::max_size.md)|Retourne la longueur maximale de la classe map.|  
|[rbegin](../Topic/map::rbegin.md)|Retourne un itérateur qui pointe vers le premier élément d'une classe map inversée.|  
|[rend](../Topic/map::rend.md)|Retourne un itérateur qui pointe vers l'emplacement après le dernier élément dans une classe map inversée.|  
|[size](../Topic/map::size.md)|Retourne le nombre d'éléments d'une classe map.|  
|[échange](../Topic/map::swap.md)|Échange les éléments de deux classes map.|  
|[upper\_bound](../Topic/map::upper_bound.md)|Retourne un itérateur au premier élément d'une classe map qui a une valeur de clé qui est supérieure ou égale à celle d'une clé spécifiée.|  
|[value\_comp](../Topic/map::value_comp.md)|Récupère une copie de l'objet de comparaison utilisé pour trier les valeurs d'éléments dans une classe map.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator&#91;&#93;](../Topic/map::operator[].md)|Insère un élément dans une classe map avec une valeur de clé spécifiée.|  
|[opérateur \=](../Topic/map::operator=.md)|Remplace les éléments d'une classe map par une copie d'une autre classe map.|  
  
## Configuration requise  
 **En\-tête :** \<map\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<map\>](http://msdn.microsoft.com/fr-fr/7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)