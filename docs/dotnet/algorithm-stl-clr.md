---
title: "algorithm (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/algorithm>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <algorithm> (STL/CLR)"
  - "en-tête <cliext/algorithm> (STL/CLR)"
  - "fonctions d'algorithme (STL/CLR)"
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# algorithm (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les fonctions de modèle de conteneur STL\/CLR qui effectuent des algorithmes.  
  
## Syntaxe  
  
```  
#include <cliext/algorithm>  
```  
  
## Fonctions  
  
|Fonction|Description|  
|--------------|-----------------|  
|[adjacent\_find](../dotnet/adjacent-find-stl-clr.md)|Recherche des deux éléments qui sont égaux.|  
|[binary\_search](../dotnet/binary-search-stl-clr.md)|Teste si une séquence ordonnée contient une valeur spécifique.|  
|[copy](../dotnet/copy-stl-clr.md)|Valeurs de copies d'une plage source à une plage de destination, itérant dans la direction par progression.|  
|[copy\_backward](../dotnet/copy-backward-stl-clr.md)|Valeurs de copies d'une plage source à une plage de destination, itérant dans la direction par progression.|  
|[count](../dotnet/count-stl-clr.md)|Retourne le nombre d'éléments dans une étendue dont les valeurs correspondent à une valeur spécifiée.|  
|[count\_if](../dotnet/count-if-stl-clr.md)|Retourne le nombre d'éléments dans une étendue dont les valeurs correspondent à une valeur spécifiée.|  
|[equal](../dotnet/equal-stl-clr.md)|Compare deux plages, élément dans l'élément.|  
|[equal\_range](../dotnet/equal-range-stl-clr.md)|Recherche une séquence ordonnée de valeurs et retourne deux positions qui délimitent une sous\-séquence de valeurs qui sont toutes égale à un élément donné.|  
|[remplissage](../dotnet/fill-stl-clr.md)|Affecte la même nouvelle valeur à chaque élément dans une plage spécifiée.|  
|[fill\_n](../dotnet/fill-n-stl-clr.md)|Assigne une nouvelle valeur à un nombre spécifié d'éléments dans une plage qui commence par un élément particulier.|  
|[rechercher](../dotnet/find-stl-clr.md)|Retourne la position de la première occurrence d'une sous\-chaîne.|  
|[find\_end](../dotnet/find-end-stl-clr.md)|Retourne le dernier sous\-séquence dans une étendue qui est identique à une séquence spécifiée.|  
|[find\_first\_of](../dotnet/find-first-of-stl-clr.md)|Recherche une plage de la première occurrence de toute d'une plage données des éléments.|  
|[find\_if](../dotnet/find-if-stl-clr.md)|Retourne la position du premier élément dans une séquence de valeurs de l'élément remplit la condition spécifiée.|  
|[for\_each](../dotnet/for-each-stl-clr.md)|Applique un objet spécifié de la fonction à chaque élément dans une séquence de valeurs et retourne l'objet de la fonction.|  
|[générer](../dotnet/generate-stl-clr.md)|Affecte les valeurs générées par un objet de la fonction à chaque élément dans une séquence de valeurs.|  
|[generate\_n](../dotnet/generate-n-stl-clr.md)|Affecte les valeurs générées par un objet de sur un nombre spécifié d'éléments.|  
|[includes](../dotnet/includes-stl-clr.md)|Teste si une plage ordonnée contient tous les éléments d'une plage triée par seconde.|  
|[inplace\_merge](../dotnet/inplace-merge-stl-clr.md)|Associe les éléments de plusieurs plages triées consécutives dans une seule plage triées.|  
|[iter\_swap](../dotnet/iter-swap-stl-clr.md)|Echange deux valeurs référencés par une paire d'itérateurs spécifiés.|  
|[lexicographical\_compare](../dotnet/lexicographical-compare-stl-clr.md)|Compare deux séquences, élément dans l'élément, qui identifie la séquence est le moins deux.|  
|[lower\_bound](../dotnet/lower-bound-stl-clr.md)|Recherche la position du premier élément dans une séquence ordonnée de valeurs qui a une valeur supérieure ou égale à une valeur spécifiée.|  
|[make\_heap](../dotnet/make-heap-stl-clr.md)|Convertit les éléments d'une plage spécifiée dans un segment de mémoire lorsque le premier élément dans le segment est le plus grand.|  
|[max](../dotnet/max-stl-clr.md)|Compare deux objets et renvoie le supérieur les deux.|  
|[max\_element](../dotnet/max-element-stl-clr.md)|Recherche le plus grand élément dans une séquence spécifiée de valeurs.|  
|[fusion](../dotnet/merge-stl-clr.md)|Combine tous les éléments de plusieurs plages sources triées dans une seule, triées plage de destination.|  
|[min](../dotnet/min-stl-clr.md)|Compare deux objets et renvoie le supérieur les deux.|  
|[min\_element](../dotnet/min-element-stl-clr.md)|Recherche le plus grand élément dans une séquence spécifiée de valeurs.|  
|[mismatch](../dotnet/mismatch-stl-clr.md)|Compare l'élément de plusieurs plages l'élément et retourne la première position où une différence se produit.|  
|[next\_permutation](../dotnet/next-permutation-stl-clr.md)|Réorganise les éléments d'une plage de sorte que le classement d'origine est remplacée par la permutation supérieure lexicographique suivante s'il existe.|  
|[nth\_element](../dotnet/nth-element-stl-clr.md)|Partitionne une plage d'éléments, en plaçant correctement le `n`ème élément de la séquence dans la plage de sorte que tous les éléments devant elle lui soient inférieurs ou égaux et tous les éléments qui la suivent dans la séquence lui soient supérieurs ou égaux.|  
|[partial\_sort](../dotnet/partial-sort-stl-clr.md)|Réorganise un nombre spécifié d'éléments plus petits dans une plage dans l'ordre nondescending.|  
|[partial\_sort\_copy](../dotnet/partial-sort-copy-stl-clr.md)|Éléments de copies d'une plage source dans une plage de destination de sorte que les éléments de la plage source sont triés.|  
|[partition](../dotnet/partition-stl-clr.md)|Organise les éléments d'une plage de sorte que les éléments qui satisfont attribut unaire précèdent ceux qui ne respecte pas le.|  
|[pop\_heap](../dotnet/pop-heap-stl-clr.md)|Déplace le plus grand élément située à début d'un segment à l'extrémité puis forme d'un nouveau segment des éléments restants.|  
|[prev\_permutation](../dotnet/prev-permutation-stl-clr.md)|Réorganise les éléments d'une plage de sorte que le classement d'origine est remplacée par la permutation supérieure lexicographique suivante s'il existe.|  
|[push\_heap](../dotnet/push-heap-stl-clr.md)|Ajoute un élément à la fin de la plage à un segment existant comprendre les éléments antérieurs dans la plage.|  
|[random\_shuffle](../dotnet/random-shuffle-stl-clr.md)|Réorganise une séquence d'éléments de `N` dans une plage dans une de `N`\! dispositions possibles sélectionnées aléatoirement.|  
|[supprimer](../dotnet/remove-stl-clr.md)|Élimine une valeur spécifiée d'une plage donnée, sans déranger l'ordre des éléments restants ni retourner la fin d'une nouvelle plage exempte de la valeur spécifiée.|  
|[remove\_copy](../dotnet/remove-copy-stl-clr.md)|Les éléments de copies d'une plage source à une plage de destination, mais les éléments d'une valeur spécifiée ne sont pas copiés, sans porter atteinte à l'ordre des éléments restants.|  
|[remove\_copy\_if](../dotnet/remove-copy-if-stl-clr.md)|Éléments de copies d'une plage source à une plage de destination, à l'exception de ceux qui satisfont un attribut, sans porter atteinte à l'ordre des éléments restants.|  
|[remove\_if](../dotnet/remove-if-stl-clr.md)|Supprime les éléments qui satisfont un attribut d'une plage données sans porter atteinte à l'ordre des éléments restants. .|  
|[remplacer](../dotnet/replace-stl-clr.md)|Remplace les éléments d'une plage qui correspondent à une valeur spécifiée avec une autre valeur.|  
|[replace\_copy](../dotnet/replace-copy-stl-clr.md)|Éléments de copies d'une plage source à une plage de destination, en remplaçant les éléments qui correspondent à une valeur spécifiée avec une autre valeur.|  
|[replace\_copy\_if](../dotnet/replace-copy-if-stl-clr.md)|Examine tous les éléments d'une plage source et le remplace en cas d'un attribut spécifié lors de la copie le résultat dans une nouvelle plage de destination.|  
|[replace\_if](../dotnet/replace-if-stl-clr.md)|Examine tous les éléments d'une plage et la remplace le cas d'un attribut spécifié.|  
|[reverse](../dotnet/reverse-stl-clr.md)|Inverse l'ordre des éléments à l'intérieur d'une rangée.|  
|[reverse\_copy](../dotnet/reverse-copy-stl-clr.md)|Inverse l'ordre des éléments dans une plage source lors de les copie dans une plage de destination.|  
|[rotate](../dotnet/rotate-stl-clr.md)|Échanger des éléments de plusieurs plages adjacentes.|  
|[rotate\_copy](../dotnet/rotate-copy-stl-clr.md)|Échange des éléments de plusieurs plages adjacentes dans une plage source et copie les résultats dans une plage de destination.|  
|[search](../dotnet/search-stl-clr.md)|Recherche la première occurrence d'une séquence dans une fourchette cible dont les éléments sont égaux à ceux dans une séquence d'éléments donnée ou dont les éléments sont équivalents dans une certaine mesure spécifiée par un attribut binaire des éléments de la séquence donnée.|  
|[search\_n](../dotnet/search-n-stl-clr.md)|Recherche la première sous\-séquence dans une plage d'un nombre spécifié d'éléments contenant une valeur particulière ou une relation à cette valeur comme spécifié par un attribut binaire.|  
|[set\_difference](../dotnet/set-difference-stl-clr.md)|Unit tous les éléments qui appartiennent à une plage source triée, mais pas à une seconde est trié la plage source, en une seule, triées plage de destination, où le respect du classement peut être spécifié par un attribut binaire.|  
|[set\_intersection](../dotnet/set-intersection-stl-clr.md)|Associe les éléments de deux plages triées consécutives dans une seule plage triée, où le respect du classement peut être spécifié par un attribut binaire.|  
|[set\_symmetric\_difference](../dotnet/set-symmetric-difference-stl-clr.md)|Associe les éléments de deux plages triées consécutives dans une seule plage triée, où le respect du classement peut être spécifié par un attribut binaire.|  
|[set\_union](../dotnet/set-union-stl-clr.md)|Associe les éléments de deux plages triées consécutives dans une seule plage triée, où le respect du classement peut être spécifié par un attribut binaire.|  
|[tri](../dotnet/sort-stl-clr.md)|\+Organise les éléments dans une plage spécifiée dans un ordre non décroissant, ou selon un critère de classement spécifié par un prédicat binaire, en parallèle.|  
|[sort\_heap](../dotnet/sort-heap-stl-clr.md)|Convertit un segment dans une plage triées.|  
|[stable\_partition](../dotnet/stable-partition-stl-clr.md)|Classe les éléments d'une plage dans deux disjointes les packages, avec ces éléments satisfaisant attribut unaire qui précèdent ceux qui ne respecte pas le, en conservant l'ordre relatif des éléments équivalents.|  
|[stable\_sort](../dotnet/stable-sort-stl-clr.md)|Organise les éléments d'une plage spécifiée dans un ordre non descendant ou selon un critère de classement spécifié par un attribut binaire et conserve l'ordre relatif des éléments équivalents.|  
|[swap](../dotnet/swap-stl-clr.md)|Échange les valeurs des éléments entre deux types d'objets, ce qui affecte le contenu du premier objet au deuxième objet et le contenu du deuxième au premier.|  
|[swap\_ranges](../dotnet/swap-ranges-stl-clr.md)|Échanger des éléments d'une plage comprenant les éléments des autres, la plage de taille à égal.|  
|[transform](../dotnet/transform-stl-clr.md)|Applique une fonction objet spécifiée à chaque élément d'une plage source ou à une paire d'éléments de de deux plages sources et copie les valeurs renvoyées de la fonction objet dans une plage de destination.|  
|[uniques](../dotnet/unique-stl-clr.md)|Supprime les éléments en double qui sont les uns â côté des autres dans une plage spécifiée.|  
|[unique\_copy](../dotnet/unique-copy-stl-clr.md)|Copie des éléments d'une plage source dans une plage de destination à l'exception des éléments en double qui sont les uns â côté des autres.|  
|[upper\_bound](../dotnet/upper-bound-stl-clr.md)|Recherche la position du premier élément dans une plage ordonnée qui a une valeur supérieure à une valeur spécifiée, où le critère de classement peut être spécifié par un prédicat binaire.|  
  
## Configuration requise  
 **En\-tête :** \<cliext\/algorithm\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)