---
title: "basic_string, classe | Microsoft Docs"
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
  - "std.basic_string"
  - "std::basic_string"
  - "basic_string"
  - "xstring/std::basic_string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_string (classe)"
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_string, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les séquences contrôlées par un objet de la classe de modèle `basic_string` correspondent à la classe de chaîne C\+\+ standard et sont généralement appelées chaînes. Toutefois, elles ne doivent pas être confondues avec les chaînes de style C se terminant par un caractère Null et utilisées dans la bibliothèque C\+\+ standard.  La chaîne C\+\+ Standard est un conteneur qui permet d'utiliser les chaînes en tant que types normaux, par exemple pour les opérations de comparaison et de concaténation, les itérateurs, les algorithmes STL, ainsi que les opérations de copie et d'assignation avec utilisation de la mémoire managée par la classe allocator.  Si vous devez convertir une chaîne C\+\+ standard en chaîne de style C se terminant par un caractère Null, utilisez le membre [basic\_string::c\_str](../Topic/basic_string::c_str.md).  
  
## Syntaxe  
  
```  
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>> class basic_string;  
```  
  
#### Paramètres  
 `CharType`  
 Type de données d'un seul caractère à stocker dans la chaîne.  La bibliothèque C\+\+ standard fournit des spécialisations de cette classe de modèle avec la [chaîne](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md) des définitions de type pour les éléments de type `char`, [wstring](../Topic/wstring.md), pour `wchar_t`, [u16string](../Topic/u16string.md) pour `char16_t` et [u32string](../Topic/u32string.md) pour `char32_t`.  
  
 `Traits`  
 Plusieurs propriétés importantes des éléments **CharType** d'une spécialisation basic\_string sont décrites par la classe **Traits**.  La valeur par défaut est `char_traits`\<`CharType`\>.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la libération de mémoire de la chaîne.  La valeur par défaut est **allocator**\<`CharType`\>.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_string](../Topic/basic_string::basic_string.md)|Construit une chaîne vide ou initialisée par des caractères spécifiques, ou qui représente une copie complète ou partielle d'un autre objet string ou d'une autre chaîne de style C.|  
  
### Typedef  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_string::allocator_type.md)|Type qui représente la classe `allocator` d'un objet string.|  
|[const\_iterator](../Topic/basic_string::const_iterator.md)|Type qui fournit un itérateur à accès aléatoire pouvant accéder à un élément `const` et le lire dans la chaîne.|  
|[const\_pointer](../Topic/basic_string::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` d'une chaîne.|  
|[const\_reference](../Topic/basic_string::const_reference.md)|Type qui fournit une référence à un élément `const` stocké dans une chaîne pour la lecture et l'exécution des opérations `const`.|  
|[const\_reverse\_iterator](../Topic/basic_string::const_reverse_iterator.md)|Type qui fournit un itérateur à accès aléatoire pouvant lire un élément `const` dans la chaîne.|  
|[difference\_type](../Topic/basic_string::difference_type.md)|Type qui fournit la différence entre deux itérateurs qui font référence aux éléments d'une même chaîne.|  
|[iterator](../Topic/basic_string::iterator.md)|Type qui fournit un itérateur à accès aléatoire pouvant lire ou modifier un élément d'une chaîne.|  
|[npos](../Topic/basic_string::npos.md)|Valeur intégrale non signée initialisée à \-1, qui indique « introuvable » ou « tous les caractères restants » quand une fonction de recherche échoue.|  
|[pointer](../Topic/basic_string::pointer.md)|Type qui fournit un pointeur vers un élément caractère d'une chaîne ou d'un tableau de caractères.|  
|[référence](../Topic/basic_string::reference.md)|Type qui fournit une référence à un élément stocké dans une chaîne.|  
|[reverse\_iterator](../Topic/basic_string::reverse_iterator.md)|Type qui fournit un itérateur à accès aléatoire pouvant lire ou modifier un élément d'une chaîne inversée.|  
|[type\_taille](../Topic/basic_string::size_type.md)|Type intégral non signé pour le nombre d'éléments d'une chaîne.|  
|[traits\_type](../Topic/basic_string::traits_type.md)|Type pour les caractéristiques de caractère des éléments stockés dans une chaîne.|  
|[value\_type](../Topic/basic_string::value_type.md)|Type qui représente le type des caractères stockés dans une chaîne.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[append](../Topic/basic_string::append.md)|Ajoute des caractères à la fin d'une chaîne.|  
|[assign](../Topic/basic_string::assign.md)|Assigne de nouvelles valeurs de caractère au contenu d'une chaîne.|  
|[at](../Topic/basic_string::at.md)|Retourne une référence à l'élément à un emplacement spécifié dans la chaîne.|  
|[back](../Topic/basic_string::back.md)||  
|[begin](../Topic/basic_string::begin.md)|Retourne un itérateur qui traite le premier élément de la chaîne.|  
|[c\_str](../Topic/basic_string::c_str.md)|Convertit le contenu d'une chaîne en chaîne de style C se terminant par un caractère Null.|  
|[capacity](../Topic/basic_string::capacity.md)|Retourne le plus grand nombre d'éléments qui peuvent être stockés dans une chaîne sans augmenter l'allocation de mémoire de la chaîne.|  
|[cbegin](../Topic/basic_string::cbegin.md)|Retourne un itérateur const qui traite le premier élément de la chaîne.|  
|[cend](../Topic/basic_string::cend.md)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'une chaîne.|  
|[clear](../Topic/basic_string::clear.md)|Efface tous les éléments d'une chaîne.|  
|[compare](../Topic/basic_string::compare.md)|Compare une chaîne à une chaîne spécifique pour déterminer si les deux chaînes sont équivalentes, ou si l'une est inférieure à l'autre d'un point de vue lexicographique.|  
|[copy](../Topic/basic_string::copy.md)|Copie tout au plus un nombre spécifique de caractères d'une position indexée dans une chaîne source vers un tableau de caractères cible.  Obsolète.  Utilisez plutôt [basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md).|  
|[crbegin](../Topic/basic_string::crbegin.md)|Retourne un itérateur const qui traite le premier élément d'une chaîne inversée.|  
|[crend](../Topic/basic_string::crend.md)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'une chaîne inversée.|  
|[\_Copy\_s](../Topic/basic_string::_Copy_s.md)|Copie tout au plus un nombre spécifique de caractères d'une position indexée dans une chaîne source vers un tableau de caractères cible.|  
|[données](../Topic/basic_string::data.md)|Convertit le contenu d'une chaîne en tableau de caractères.|  
|[empty](../Topic/basic_string::empty.md)|Effectue un test pour déterminer si la chaîne contient des caractères.|  
|[end](../Topic/basic_string::end.md)|Retourne un itérateur qui traite l'emplacement qui suit le dernier élément d'une chaîne.|  
|[erase](../Topic/basic_string::erase.md)|Supprime un élément ou une plage d'éléments dans une chaîne à partir de l'emplacement spécifié.|  
|[find](../Topic/basic_string::find.md)|Recherche une chaîne vers l'avant pour trouver la première occurrence d'une sous\-chaîne qui correspond à une séquence spécifique de caractères.|  
|[find\_first\_not\_of](../Topic/basic_string::find_first_not_of.md)|Recherche dans une chaîne le premier caractère qui n'est pas un élément de la chaîne spécifiée.|  
|[find\_first\_of](../Topic/basic_string::find_first_of.md)|Recherche dans une chaîne le premier caractère qui correspond à un élément de la chaîne spécifiée.|  
|[find\_last\_not\_of](../Topic/basic_string::find_last_not_of.md)|Recherche dans une chaîne le dernier caractère qui n'est pas un élément de la chaîne spécifiée.|  
|[find\_last\_of](../Topic/basic_string::find_last_of.md)|Recherche dans une chaîne le dernier caractère qui est un élément de la chaîne spécifiée.|  
|[front](../Topic/basic_string::front.md)|Retourne une référence au premier élément d'une chaîne.|  
|[get\_allocator](../Topic/basic_string::get_allocator.md)|Retourne une copie de l'objet `allocator` utilisé pour construire la chaîne.|  
|[insert](../Topic/basic_string::insert.md)|Insère un élément, un certain nombre d'éléments ou une plage d'éléments dans la chaîne à la position spécifiée.|  
|[length](../Topic/basic_string::length.md)|Retourne le nombre actuel d'éléments contenus dans une chaîne.|  
|[max\_size](../Topic/basic_string::max_size.md)|Retourne le nombre maximal de caractères qu'une chaîne peut contenir.|  
|[pop\_back](../Topic/basic_string::pop_back.md)|Efface le dernier élément de la chaîne.|  
|[push\_back](../Topic/basic_string::push_back.md)|Ajoute un élément à la fin de la chaîne.|  
|[rbegin](../Topic/basic_string::rbegin.md)|Retourne un itérateur au premier élément d'une chaîne inversée.|  
|[rend](../Topic/basic_string::rend.md)|Retourne un itérateur qui pointe juste après le dernier élément d'une chaîne inversée.|  
|[replace](../Topic/basic_string::replace.md)|Remplace les éléments d'une chaîne à la position spécifiée par des caractères spécifiques ou des caractères copiés à partir d'autres plages, chaînes ou chaînes de style C.|  
|[reserve](../Topic/basic_string::reserve.md)|Définit la capacité de la chaîne en fonction d'un nombre au moins aussi grand que le nombre spécifié.|  
|[resize](../Topic/basic_string::resize.md)|Spécifie une nouvelle taille pour une chaîne, en ajoutant ou en effaçant des éléments selon les besoins.|  
|[rfind](../Topic/basic_string::rfind.md)|Recherche une chaîne vers l'arrière pour trouver la première occurrence d'une sous\-chaîne qui correspond à une séquence spécifique de caractères.|  
|[shrink\_to\_fit](../Topic/basic_string::shrink_to_fit.md)|Ignore la capacité excédentaire de la chaîne.|  
|[size](../Topic/basic_string::size.md)|Retourne le nombre actuel d'éléments contenus dans une chaîne.|  
|[substr](../Topic/basic_string::substr.md)|Copie une sous\-chaîne d'un certain nombre de caractères dans une chaîne qui commence à la position spécifiée.|  
|[échange](../Topic/basic_string::swap.md)|Échange le contenu de deux chaînes.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \+\=](../Topic/basic_string::operator+=.md)|Ajoute des caractères à une chaîne.|  
|[opérateur \=](../Topic/basic_string::operator=.md)|Assigne de nouvelles valeurs de caractère au contenu d'une chaîne.|  
|[operator&#91;&#93;](../Topic/basic_string::operator.md)|Fournit une référence au caractère situé à l'index spécifié dans une chaîne.|  
  
## Notes  
 Si une fonction doit générer une séquence supérieure au nombre maximal d'éléments \([max\_size](../Topic/basic_string::max_size.md)\), la fonction signale une erreur de longueur en levant un objet de type [length\_error](../standard-library/length-error-class.md).  
  
 Les références, pointeurs et itérateurs qui désignent les éléments de la séquence contrôlée peuvent devenir non valides après un appel à une fonction qui change la séquence contrôlée, ou après le premier appel à une fonction membre non **const**.  
  
## Configuration requise  
 **En\-tête :** \<string\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<string\>](../standard-library/string.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)