---
title: "&lt;iterator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<iterator>"
  - "std.<iterator>"
  - "<iterator>"
  - "iterator/std::<iterator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterateur (en-tête)"
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# &lt;iterator&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les primitives des itérateurs, les itérateurs prédéfinis et les itérateurs de flux, ainsi que plusieurs modèles de prise en charge.  Les itérateurs prédéfinis incluent des adaptateurs d'insertion et d'inversion.  Il existe trois classes d'adaptateurs d'itérateur d'insertion : avant, arrière et général.  Ils fournissent une sémantique d'insertion, différente de la sémantique de remplacement que les itérateurs de fonctions membres de conteneurs fournissent.  
  
## Syntaxe  
  
```  
  
#include <iterator>  
  
```  
  
## Notes  
 Les itérateurs sont une généralisation des pointeurs qui s'abstrait de leurs contraintes de telle sorte qu'un programme C\+\+ puisse gérer différentes structures de données de manière uniforme.  Les itérateurs se comportent comme des intermédiaires entre les conteneurs et les algorithmes génériques.  Au lieu de traiter des types de données spécifiques, les algorithmes sont définis pour traiter une plage spécifiée par un type d'itérateur.  Toute structure de données répondant aux exigences de l'itérateur peut être traitée par l'algorithme.  Il existe cinq types ou catégories d'itérateur, chacun possédant son propre ensemble d'exigences et de fonctionnalités résultantes :  
  
-   De sortie : se déplace vers l'avant, peut stocker mais pas récupérer des valeurs, fourni par ostream et inserter.  
  
-   D'entrée : se déplace vers l'avant, peut récupérer mais pas stocker des valeurs, fourni par istream.  
  
-   D'avance : se déplace vers l'avant, peut stocker et récupérer des valeurs.  
  
-   Bidirectionnel : se déplace vers l'avant et l'arrière, peut stocker et récupérer des valeurs, fourni par list, set, multiset, map et multimap.  
  
-   D'accès aléatoire : éléments accessibles dans n'importe quel ordre, peut stocker et récupérer des valeurs, fourni par vector, deque, string et array.  
  
 Les itérateurs qui ont des exigences supérieures et disposent d'un accès plus performant aux éléments peuvent être utilisés à la place d'itérateurs ayant moins d'exigences.  Par exemple, si un itérateur d'avance est appelé, alors un itérateur d'accès aléatoire peut être utilisé à la place.  
  
 Visual Studio ajoute des extensions aux itérateurs de la bibliothèque C\+\+ standard pour prendre en charge diverses situations en mode débogage pour les itérateurs vérifiés et non vérifiés.  Pour plus d'informations, consultez [Bibliothèques sécurisées : bibliothèque C\+\+ standard](../standard-library/safe-libraries-cpp-standard-library.md).  
  
### Fonctions  
  
|||  
|-|-|  
|[advance](../Topic/advance.md)|Incrémente un itérateur d'un nombre spécifié de positions.|  
|[back\_inserter](../Topic/back_inserter.md)|Crée un itérateur qui peut insérer des éléments à la fin d'un conteneur spécifié.|  
|[begin](../Topic/begin.md)|Récupère un itérateur sur le premier élément d'un conteneur spécifié.|  
|[cbegin](../Topic/cbegin.md)|Récupère un itérateur constant sur le premier élément d'un conteneur spécifié.|  
|[cend](../Topic/cend.md)|Récupère un itérateur constant sur l'élément qui suit le dernier élément dans le conteneur spécifié.|  
|[distance](../Topic/distance.md)|Détermine le nombre d'incréments entre les positions traitées par deux itérateurs.|  
|[end](../Topic/end.md)|Récupère un itérateur de l'élément qui suit le dernier élément dans le conteneur spécifié.|  
|[front\_inserter](../Topic/front_inserter.md)|Crée un itérateur qui peut insérer des éléments à l'avant d'un conteneur spécifié.|  
|[inserter](../Topic/inserter.md)|Adaptateur d'itérateur qui ajoute un nouvel élément à un conteneur à un point d'insertion donné.|  
|[make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)|Crée un [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md) qui peut être utilisé par d'autres algorithmes. **Note:**  Cette fonction est une extension Microsoft de la bibliothèque C\+\+ standard.  Le code implémenté à l'aide de cette fonction ne peut pas être utilisé dans les environnements de build C\+\+ standard qui ne prennent pas en charge cette extension Microsoft.|  
|[make\_move\_iterator](../Topic/make_move_iterator.md)|Retourne un itérateur de déplacement contenant l'itérateur fourni en tant qu'itérateur de base stocké.|  
|[make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)|Crée un [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md) qui peut être utilisé par d'autres algorithmes. **Note:**  Cette fonction est une extension Microsoft de la bibliothèque C\+\+ standard.  Le code implémenté à l'aide de cette fonction ne peut pas être utilisé dans les environnements de build C\+\+ standard qui ne prennent pas en charge cette extension Microsoft.|  
|[next](../Topic/next.md)|Itère un nombre de fois donné et retourne la nouvelle position de l'itérateur.|  
|[prev](../Topic/prev.md)|Itère en sens inverse un nombre de fois donné et retourne la nouvelle position de l'itérateur.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Citerator%3E\).md)|Teste si l'objet itérateur situé à gauche de l'opérateur n'est pas égal à l'objet itérateur situé à droite.|  
|[operator\=\=](../Topic/operator==%20\(%3Citerator%3E\).md)|Teste si l'objet itérateur situé à gauche de l'opérateur est égal à l'objet itérateur situé à droite.|  
|[operator\<](../Topic/operator%3C%20\(%3Citerator%3E\).md)|Teste si l'objet itérateur situé à gauche de l'opérateur est inférieur à l'objet itérateur situé à droite.|  
|[operator\<\=](../Topic/operator%3C=%20\(%3Citerator%3E\).md)|Teste si l'objet itérateur situé à gauche de l'opérateur est inférieur ou égal à l'objet itérateur situé à droite.|  
|[operator\>](../Topic/operator%3E%20\(%3Citerator%3E\).md)|Teste si l'objet itérateur situé à gauche de l'opérateur est supérieur à l'objet itérateur situé à droite.|  
|[operator\>\=](../Topic/operator%3E=%20\(%3Citerator%3E\).md)|Teste si l'objet itérateur situé à gauche de l'opérateur est supérieur ou égal à l'objet itérateur situé à droite.|  
|[operator\+](../Topic/operator+%20\(%3Citerator%3E\).md)|Ajoute un décalage à un itérateur et retourne le nouvel `reverse_iterator` qui se rapporte à l'élément inséré à la nouvelle position décalée.|  
|[operator\-](../Topic/operator-%20\(%3Citerator%3E\).md)|Soustrait un itérateur à un autre et retourne la différence.|  
  
### Classes  
  
|||  
|-|-|  
|[back\_insert\_iterator](../standard-library/back-insert-iterator-class.md)|Cette classe de modèle décrit un objet itérateur de sortie.  Elle insère des éléments dans un conteneur de type **Conteneur**, auquel elle accède via l'objet **pointeur** protégé qu'elle stocke sous le nom de conteneur.|  
|[bidirectional\_iterator\_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur bidirectionnel.|  
|[checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)|Classe qui accède à un tableau en utilisant un itérateur vérifié d'accès aléatoire. **Note:**  Cette classe est une extension Microsoft de la bibliothèque C\+\+ standard.  Le code implémenté à l'aide de cette fonction ne peut pas être utilisé dans les environnements de build C\+\+ standard qui ne prennent pas en charge cette extension Microsoft.|  
|[forward\_iterator\_tag](../standard-library/forward-iterator-tag-struct.md)|Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur d'avance.|  
|[front\_insert\_iterator](../standard-library/front-insert-iterator-class.md)|Cette classe de modèle décrit un objet itérateur de sortie.  Elle insère des éléments dans un conteneur de type **Conteneur**, auquel elle accède via l'objet **pointeur** protégé qu'elle stocke sous le nom de conteneur.|  
|[input\_iterator\_tag](../standard-library/input-iterator-tag-struct.md)|Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur d'entrée.|  
|[insert\_iterator](../standard-library/insert-iterator-class.md)|Cette classe de modèle décrit un objet itérateur de sortie.  Elle insère des éléments dans un conteneur de type **Conteneur**, auquel elle accède via l'objet **pointeur** protégé qu'elle stocke sous le nom de conteneur.  Elle stocke également l'objet **itérateur** protégé, issu de la classe **Container::iterator**, appelé **iter**.|  
|[istream\_iterator](../standard-library/istream-iterator-class.md)|Cette classe de modèle décrit un objet itérateur d'entrée.  Elle extrait des objets de classe **Ty** d'un flux d'entrée, auquel elle accède via un objet qu'elle stocke, de type pointeur vers `basic_istream`\<**Elem**, **Tr**\>.|  
|[istreambuf\_iterator](../standard-library/istreambuf-iterator-class.md)|Cette classe de modèle décrit un objet itérateur d'entrée.  Elle insère des éléments de classe **Elem** dans une mémoire tampon de flux de sortie, à laquelle elle accède via un objet qu'elle stocke, de type **pointeur** vers `basic_streambuf`\<**Elem**, **Tr**\>.|  
|[iterator](../standard-library/iterator-struct.md)|Cette classe de modèle est utilisée comme type de base pour tous les itérateurs.|  
|[iterator\_traits](../standard-library/iterator-traits-struct.md)|Classe d'assistance de modèle fournissant des types critiques qui sont associés à différents types d'itérateur afin de pouvoir être référencés de la même façon.|  
|[move\_iterator](../standard-library/move-iterator-class.md)|Un objet `move_iterator` stocke un itérateur d'accès aléatoire de type `RandomIterator`.  Il se comporte comme un itérateur d'accès aléatoire, sauf lorsqu'il est déréférencé.  Le résultat de `operator*` est implicitement casté en `value_type&&:` pour créer une `rvalue reference`.|  
|[ostream\_iterator](../standard-library/ostream-iterator-class.md)|Cette classe de modèle décrit un objet itérateur de sortie.  Elle insère des objets de classe **Type** dans un flux de sortie, auquel elle accède via un objet qu'elle stocke, de type **pointeur** vers `basic_ostream`\<**Elem**, **Tr**\>.|  
|[ostreambuf\_iterator](../standard-library/ostreambuf-iterator-class.md)|Cette classe de modèle décrit un objet itérateur de sortie.  Elle insère des éléments de classe **Elem** dans une mémoire tampon de flux de sortie, à laquelle elle accède via un objet qu'elle stocke, de type pointeur vers `basic_streambuf`\<**Elem**, **Tr**\>.|  
|[output\_iterator\_tag](../standard-library/output-iterator-tag-struct.md)|Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur de sortie.|  
|[random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md)|Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur d'accès aléatoire.|  
|[reverse\_iterator](../standard-library/reverse-iterator-class.md)|Cette classe de modèle décrit un objet qui se comporte comme un itérateur d'accès aléatoire, mais en sens inverse.|  
|[unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)|Classe qui accède à un tableau en utilisant un itérateur non vérifié d'accès aléatoire. **Note:**  Cette classe est une extension Microsoft de la bibliothèque C\+\+ standard.  Le code implémenté à l'aide de cette fonction ne peut pas être utilisé dans les environnements de build C\+\+ standard qui ne prennent pas en charge cette extension Microsoft.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)