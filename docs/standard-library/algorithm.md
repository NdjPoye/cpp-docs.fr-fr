---
title: "&lt;algorithm&gt; | Microsoft Docs"
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
  - "<algorithm>"
  - "std::<algorithm>"
  - "algorithm/std::<algorithm>"
  - "std.<algorithm>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <algorithm>"
  - "en-tête d'algorithme (C++)"
  - "bibliothèque C++ standard, algorithmes"
ms.assetid: 19f97711-7a67-4a65-8fd1-9a2bd3ca327d
caps.latest.revision: 23
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;algorithm&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les fonctions de modèle du conteneur STL qui exécutent des algorithmes.  
  
## Syntaxe  
  
```  
(see relevant links below for specific algorithm syntax)  
```  
  
## Notes  
 Les algorithmes STL sont génériques, car ils peuvent traiter diverses structures de données.  Les structures de données qu'ils peuvent traiter incluent non seulement les classes de conteneur STL, telles que `vector` et `list`, mais aussi les structures de données définies par programme et les tableaux d'éléments qui répondent aux exigences d'un algorithme en particulier.  Les algorithmes STL atteignent ce niveau de généralité en parcourant les éléments d'un conteneur indirectement, via des itérateurs.  
  
 Les algorithmes STL traitent les plages d'itérateurs qui sont généralement spécifiées par leur position de début ou de fin.  Les plages référencées doivent être valides, c'est\-à\-dire que tous les pointeurs de ces plages doivent pouvoir être déréférencés et, que dans les séquences de chaque plage, la dernière position doit être accessible depuis la première par incrémentation.  
  
 Les algorithmes STL étendent les actions prises en charge par les opérations et les fonctions membres de chaque conteneur STL, et permettent, entre autres choses, l'utilisation simultanée de plusieurs types d'objets conteneurs.  Deux suffixes ont été utilisés pour transmettre des informations concernant l'usage des algorithmes.  
  
-   Le suffixe `_if` indique que l'algorithme est utilisé avec des objets de fonction opérant sur les valeurs des éléments plutôt que sur les éléments eux\-mêmes.  L'algorithme `find_if` recherche les éléments dont les valeurs répondent au critère spécifié par un objet de fonction, et l'algorithme `find` recherche une valeur particulière.  
  
-   Le suffixe \_copy indique que l'algorithme manipule les valeurs des éléments, mais copie également les valeurs modifiées dans une plage de destination.  L'algorithme `reverse` inverse l'ordre des éléments d'une plage, et l'algorithme `reverse_copy` copie également le résultat dans une plage de destination.  
  
 Les algorithmes STL sont généralement classés par groupes selon leur usage ou leurs exigences.  Il s'agit notamment des algorithmes de modification qui changent la valeur des éléments, contrairement aux autres algorithmes.  Les algorithmes de mutation modifient l'ordre des éléments, mais pas leurs valeurs.  Les algorithmes de suppression peuvent éliminer les éléments d'une plage ou d'une copie d'une plage.  Les algorithmes de tri modifient l'ordre des éléments d'une plage de plusieurs façons, et les algorithmes de plages triées agissent uniquement sur les plages dont les éléments ont été triés d'une certaine manière.  
  
 Les algorithmes STL numériques fournis pour le traitement numérique possèdent leur propre fichier d'en\-tête [\<numeric\>](../standard-library/numeric.md). Les objets de fonction et les adaptateurs, quant à eux, sont définis dans l'en\-tête [\<functional\>](../standard-library/functional.md). Les objets de fonction qui renvoient des valeurs booléennes sont appelés prédicats.  Le prédicat binaire par défaut est le `operator<` de comparaison.  En général, les éléments qui sont triés ne doivent pas être équivalents, afin que, avec deux éléments quelconques donnés, il soit possible de déterminer qu'ils sont équivalents \(dans le sens où l'un n'est pas inférieur à l'autre\) ou que l'un est inférieur à l'autre.  Cela entraîne un tri des éléments non équivalents.  
  
### Fonctions  
  
|||  
|-|-|  
|[adjacent\_find](../Topic/adjacent_find.md)|Recherche deux éléments adjacents qui ont la même valeur ou qui répondent à une condition spécifiée.|  
|[all\_of](../Topic/all_of.md)|Retourne `true` lorsqu'une condition est remplie pour chaque élément de la plage spécifiée.|  
|[any\_of](../Topic/any_of.md)|Retourne `true` lorsqu'une condition est remplie au moins une fois dans la plage d'éléments spécifiée.|  
|[binary\_search](../Topic/binary_search.md)|Teste si un élément d'une plage triée est égal à une valeur spécifiée ou équivalent, selon une condition spécifiée par un prédicat binaire.|  
|[copy](../Topic/copy.md)|Assigne les valeurs des éléments d'une plage source à une plage de destination, en procédant à une itération via la séquence source d'éléments et en leur assignant de nouvelles positions, du haut vers le bas.|  
|[copy\_backward](../Topic/copy_backward.md)|Assigne les valeurs des éléments d'une plage source à une plage de destination, en procédant à une itération via la séquence source d'éléments et en leur assignant de nouvelles positions vers le haut.|  
|[copy\_if](../Topic/copy_if.md)|Copie tous les éléments d'une plage donnée qui renvoient la valeur `true` pour une condition spécifiée.|  
|[copy\_n](../Topic/copy_n.md)|Copie un nombre spécifié d'éléments.|  
|[count](../Topic/count.md)|Retourne le nombre d'éléments d'une plage dont les valeurs correspondent à une valeur spécifiée.|  
|[count\_if](../Topic/count_if.md)|Retourne le nombre d'éléments d'une plage dont les valeurs correspondent à une condition spécifiée.|  
|[equal](../Topic/equal.md)|Compare deux plages, élément par élément, à la recherche d'une égalité ou d'une équivalence, selon une condition spécifiée par un prédicat binaire.|  
|[equal\_range](../Topic/equal_range.md)|Recherche une paire de positions dans une plage triée. La première inférieure ou équivalente à la position d'un élément spécifié, et la deuxième supérieure à la position de cet élément. L'équivalence ou le tri utilisés pour établir des positions dans la séquence peuvent être spécifiés par un prédicat binaire.|  
|[fill](../Topic/fill.md)|Affecte la même nouvelle valeur à chaque élément d'une plage spécifiée.|  
|[fill\_n](../Topic/fill_n.md)|Assigne une nouvelle valeur à un nombre spécifié d'éléments d'une plage qui commence par un élément particulier.|  
|[find](../Topic/find%20\(STL\).md)|Recherche la position de la première occurrence d'un élément d'une plage ayant une valeur spécifiée.|  
|[find\_end](../Topic/find_end.md)|Recherche dans une plage la dernière sous\-séquence qui est identique à une séquence spécifiée ou qui est équivalente, selon une condition spécifiée par un prédicat binaire.|  
|[find\_first\_of](../Topic/find_first_of.md)|Recherche la première occurrence parmi plusieurs valeurs d'une plage cible, ou la première occurrence parmi plusieurs éléments qui sont équivalents, selon une condition spécifiée par un prédicat binaire, à un ensemble d'éléments spécifiés.|  
|[find\_if](../Topic/find_if.md)|Recherche la position de la première occurrence d'un élément d'une plage qui répond à une condition spécifiée.|  
|[find\_if\_not](../Topic/find_if_not.md)|Retourne le premier élément d'une plage spécifiée qui ne répond pas à une condition.|  
|[for\_each](../Topic/for_each.md)|Applique un objet de fonction spécifié à chaque élément d'une plage, du haut vers le bas, et retourne l'objet de la fonction.|  
|[generate](../Topic/generate.md)|Assigne les valeurs générées par un objet de fonction à chaque élément d'une plage.|  
|[generate\_n](../Topic/generate_n.md)|Assigne les valeurs générées par un objet de fonction à un nombre spécifié d'éléments d'une plage, et retourne à la position située juste après la dernière valeur assignée.|  
|[includes](../Topic/includes.md)|Teste si une plage triée contient tous les éléments d'une autre plage triée. Le critère de tri ou d'équivalence entre les éléments peut être spécifié par un prédicat binaire.|  
|[inplace\_merge](../Topic/inplace_merge.md)|Regroupe les éléments de deux plages triées consécutives au sein d'une même plage triée. Le critère de tri peut être spécifié par un prédicat binaire.|  
|[is\_heap](../Topic/is_heap.md)|Retourne `true` si les éléments d'une plage spécifiée forment un tas.|  
|[is\_heap\_until](../Topic/is_heap_until.md)|Retourne `true` si la plage spécifiée forme un tas jusqu'au dernier élément.|  
|[is\_partitioned](../Topic/is_partitioned.md)|Retourne `true` si tous les éléments d'une plage qui renvoient la valeur `true` pour une condition donnée, se trouvent avant les éléments qui renvoient la valeur `false`.|  
|[is\_permutation](../Topic/is_permutation.md)|Détermine si les éléments d'une plage donnée forment une permutation valide.|  
|[is\_sorted](../Topic/is_sorted.md)|Retourne `true` si les éléments de la plage spécifiée sont triés.|  
|[is\_sorted\_until](../Topic/is_sorted_until.md)|Retourne `true` si les éléments de la plage spécifiée sont triés.|  
|[iter\_swap](../Topic/iter_swap.md)|Échange deux valeurs référencées par une paire d'itérateurs spécifiés.|  
|[lexicographical\_compare](../Topic/lexicographical_compare.md)|Compare deux séquences, élément par élément, pour déterminer lequel est inférieur à l'autre.|  
|[lower\_bound](../Topic/lower_bound.md)|Recherche la position du premier élément d'une plage triée dont la valeur est supérieure ou équivalente à une valeur spécifiée. Le critère de tri peut être spécifié par un prédicat binaire.|  
|[make\_heap](../Topic/make_heap.md)|Convertit les éléments d'une plage spécifiée en un tas, dans lequel le premier élément est le plus grand, et pour lequel un critère de tri peut être spécifié à l'aide d'un prédicat binaire.|  
|[max](../Topic/max.md)|Compare deux objets et retourne le plus grand des deux. Un critère de tri peut être spécifié à l'aide d'un prédicat binaire.|  
|[max\_element](../Topic/max_element.md)|Recherche la première occurrence du plus grand élément dans une plage spécifiée. Un critère de tri peut être spécifié par un prédicat binaire.|  
|[merge](../Topic/merge.md)|Regroupe tous les éléments de deux plages sources triées au sein d'une même plage de destination triée. Le critère de tri peut être spécifié par un prédicat binaire.|  
|[min](../Topic/min.md)|Compare deux objets et retourne le plus petit des deux. Un critère de tri peut être spécifié à l'aide d'un prédicat binaire.|  
|[min\_element](../Topic/min_element.md)|Recherche la première occurrence du plus petit élément dans une plage spécifiée. Un critère de tri peut être spécifié par un prédicat binaire.|  
|[minmax](../Topic/minmax.md)|Compare deux paramètres d'entrée et les retourne en tant que paire, du plus petit au plus grand.|  
|[minmax\_element](../Topic/minmax_element.md)|Exécute le travail effectué par [min\_element](../Topic/min_element.md) et [max\_element](../Topic/max_element.md) au sein d'un même appel.|  
|[mismatch](../Topic/mismatch.md)|Compare deux plages, élément par élément, à la recherche d'une égalité ou d'une équivalence, selon une condition spécifiée par un prédicat binaire, et recherche la première position où se trouve une différence.|  
|[move](../Topic/%3Calg%3E%20move.md)|Déplace les éléments associés à une plage spécifiée.|  
|[move\_backward](../Topic/move_backward.md)|Déplace les éléments d'un itérateur vers un autre.  Le déplacement commence par le dernier élément d'une plage spécifiée, et se termine par le premier élément de cette plage.|  
|[next\_permutation](../Topic/next_permutation.md)|Réorganise les éléments d'une plage, de sorte que le tri d'origine soit remplacé par la prochaine permutation plus élevée d'un point de vue lexicographique \(s'il en existe une\). La notion de "prochaine" peut être définie à l'aide d'un prédicat binaire.|  
|[none\_of](../Topic/none_of.md)|Retourne `true` lorsqu'une condition n'est remplie par aucun des éléments d'une plage spécifiée.|  
|[nth\_element](../Topic/nth_element.md)|Divise une plage d'éléments, en recherchant le *n*ième élément de la séquence dans la plage, de sorte que tous les éléments le précédant lui soient inférieurs ou égaux, et que tous les éléments qui le suivent lui soient supérieurs ou égaux.|  
|[partial\_sort](../Topic/partial_sort.md)|Réorganise un nombre spécifié d'éléments plus petits au sein d'une plage, dans un ordre non décroissant, ou selon un critère de tri spécifié par un prédicat binaire.|  
|[partial\_sort\_copy](../Topic/partial_sort_copy.md)|Copie les éléments d'une plage source dans une plage de destination. Les éléments sources sont triés par ordre croissant ou selon un autre prédicat binaire spécifié.|  
|[partition](../Topic/partition.md)|Répartit les éléments d'une plage en deux ensembles disjoints. Les éléments qui répondent à un prédicat unaire doivent précéder ceux qui n'y répondent pas.|  
|[partition\_copy](../Topic/partition_copy.md)|Copie les éléments qui renvoient la valeur `true` dans une destination pour une condition donnée, et qui renvoient la valeur `false` dans une autre destination.  Les éléments doivent provenir d'une plage spécifiée.|  
|[partition\_point](../Topic/partition_point.md)|Retourne le premier élément d'une plage donnée qui ne répond pas à une condition.  Les éléments sont triés de sorte que ceux qui répondent à la condition précèdent ceux qui n'y répondent pas.|  
|[pop\_heap](../Topic/pop_heap.md)|Retire le plus grand élément du début du tas et le place à l'avant\-dernière position de la plage, puis forme un nouveau tas à partir des éléments restants.|  
|[prev\_permutation](../Topic/prev_permutation.md)|Réorganise les éléments d'une plage, de sorte que le tri d'origine soit remplacé par la prochaine permutation plus élevée d'un point de vue lexicographique \(s'il en existe une\). La notion de "prochaine" peut être définie à l'aide d'un prédicat binaire.|  
|[push\_heap](../Topic/push_heap.md)|Ajoute un élément qui se trouve à la fin d'une plage à un tas existant, constitué des éléments précédents de la plage.|  
|[random\_shuffle](../Topic/random_shuffle.md)|Réorganise une séquence de *N* éléments d'une plage en *N*\!  dispositions possibles, sélectionnées de manière aléatoire.|  
|[remove](../Topic/remove.md)|Élimine une valeur spécifiée d'une plage donnée sans modifier l'ordre des éléments restants, et retourne la fin d'une nouvelle plage exempte de la valeur spécifiée.|  
|[remove\_copy](../Topic/remove_copy.md)|Copie les éléments d'une plage source vers une plage de destination. Les éléments ayant une valeur spécifiée ne sont pas copiés. L'ordre des éléments restants n'est pas modifié et la fin d'une nouvelle plage de destination est retournée.|  
|[remove\_copy\_if](../Topic/remove_copy_if.md)|Copie les éléments d'une plage source vers une plage de destination. Les éléments répondant à un prédicat ne sont pas copiés. L'ordre des éléments restants n'est pas modifié et la fin d'une nouvelle plage de destination est retournée.|  
|[remove\_if](../Topic/remove_if.md)|Élimine d'une plage donnée les éléments qui répondent à un prédicat, sans modifier l'ordre des éléments restants et en retournant la fin d'une nouvelle plage exempte de la valeur spécifiée.|  
|[replace](../Topic/replace.md)|Examine tous les éléments d'une plage et les remplace s'ils correspondent à une valeur spécifiée.|  
|[replace\_copy](../Topic/replace_copy.md)|Examine tous les éléments d'une plage source et les remplace s'ils correspondent à une valeur spécifiée, tout en copiant le résultat dans une nouvelle plage de destination.|  
|[replace\_copy\_if](../Topic/replace_copy_if.md)|Examine tous les éléments d'une plage source et les remplace s'ils répondent à un prédicat, tout en copiant le résultat dans une nouvelle plage de destination.|  
|[replace\_if](../Topic/replace_if.md)|Examine tous les éléments d'une plage et les remplace s'ils répondent à un prédicat spécifié.|  
|[reverse](../Topic/reverse.md)|Inverse l'ordre des éléments d'une plage.|  
|[reverse\_copy](../Topic/reverse_copy.md)|Inverse l'ordre des éléments d'une plage source, tout en les copiant dans une plage de destination.|  
|[rotate](../Topic/rotate.md)|Échange les éléments de deux plages adjacentes.|  
|[rotate\_copy](../Topic/rotate_copy.md)|Échange les éléments de deux plages adjacentes au sein d'une plage source et copie le résultat dans une plage de destination.|  
|[search](../Topic/search.md)|Recherche la première occurrence d'une séquence au sein d'une plage cible dont les éléments sont égaux à ceux d'une séquence d'éléments donnée ou dont les éléments sont équivalents à ceux d'une séquence donnée, selon un prédicat binaire spécifié.|  
|[search\_n](../Topic/search_n.md)|Recherche la première sous\-séquence d'une plage dont un nombre spécifié d'éléments ont une valeur particulière ou une relation à cette valeur, selon un prédicat binaire spécifié.|  
|[set\_difference](../Topic/set_difference.md)|Regroupe tous les éléments qui appartiennent à une plage source triée, mais pas à une autre plage source triée, en une même plage de destination triée. Un critère de tri peut être spécifié par un prédicat binaire.|  
|[set\_intersection](../Topic/set_intersection.md)|Regroupe tous les éléments de deux plages sources triées au sein d'une même plage de destination triée. Le critère de tri peut être spécifié par un prédicat binaire.|  
|[set\_symmetric\_difference](../Topic/set_symmetric_difference.md)|Regroupe tous les éléments qui appartiennent à l'une de deux plages sources triées \(mais pas aux deux\) au sein d'une même plage de destination triée. Le critère de tri peut être spécifié par un prédicat binaire.|  
|[set\_union](../Topic/set_union.md)|Regroupe tous les éléments qui appartiennent au moins à l'une de deux plages sources triées au sein d'une même plage de destination triée. Le critère de tri peut être spécifié par un prédicat binaire.|  
|[sort](../Topic/sort.md)|Réorganise les éléments d'une plage spécifiée, dans un ordre non décroissant, ou selon un critère de tri spécifié par un prédicat binaire.|  
|[shuffle](../Topic/std::shuffle.md)|Lit de façon aléatoire \(réorganise\) les éléments pour une plage donnée à l'aide d'un générateur de nombres aléatoires.|  
|[sort\_heap](../Topic/sort_heap.md)|Convertit un tas en une plage triée.|  
|[stable\_partition](../Topic/stable_partition.md)|Classe les éléments d'une plage en deux ensembles disjoints. Les éléments qui répondent à un prédicat unaire doivent précéder ceux qui n'y répondent pas, et l'ordre relatif des éléments équivalents doit être conservé.|  
|[stable\_sort](../Topic/stable_sort.md)|Classe les éléments d'une plage spécifiée dans un ordre non décroissant, ou selon un critère de tri spécifié par un prédicat binaire, et conserve l'ordre relatif des éléments équivalents.|  
|[échange](../Topic/swap.md)|Échange les valeurs des éléments de deux types d'objets, en assignant le contenu du premier objet au deuxième objet, et le contenu du deuxième au premier.|  
|[swap\_ranges](../Topic/swap_ranges.md)|Échange les éléments d'une plage avec ceux d'une autre plage de taille égale.|  
|[transformation](../Topic/transform.md)|Applique un objet de fonction spécifié à chaque élément d'une plage source ou à une paire d'éléments de deux plages sources, et copie les valeurs renvoyées de l'objet de fonction dans une plage de destination.|  
|[unique](../Topic/unique%20\(%3Calgorithm%3E\).md)|Supprime les éléments en double adjacents dans une plage spécifiée.|  
|[unique\_copy](../Topic/unique_copy.md)|Copie les éléments d'une plage source dans une plage de destination, à l'exception des éléments en double adjacents.|  
|[upper\_bound](../Topic/upper_bound.md)|Recherche la position du premier élément d'une plage triée dont la valeur est supérieure à une valeur spécifiée. Le critère de tri peut être spécifié par un prédicat binaire.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)