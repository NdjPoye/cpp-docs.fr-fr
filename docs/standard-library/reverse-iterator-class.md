---
title: "reverse_iterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "reverse_iterator"
  - "std::reverse_iterator"
  - "std.reverse_iterator"
  - "xutility/std::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator (classe)"
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# reverse_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle est un adaptateur d'itérateur qui décrit un objet itérateur inverse qui se comporte comme un itérateur d'accès aléatoire ou bidirectionnel, mais en sens inverse.  Elle permet de parcourir une plage à reculons.  
  
## Syntaxe  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### Paramètres  
 RandomIterator  
 Type qui représente l'itérateur à adapter pour un fonctionnement en sens inverse.  
  
## Notes  
 Les conteneurs existants dans la bibliothèque STL \(Standard Template Library\) définissent également les types `reverse_iterator` et `const_reverse_iterator`, et possèdent les fonctions membres `rbegin` et `rend` qui retournent des itérateurs inverses.  Ces itérateurs ont une sémantique de remplacement.  L'adaptateur `reverse_iterator` complète cette fonctionnalité en tant que sémantique d'insertion d'offres et peut également être utilisé avec des flux.  
  
 Les `reverse_iterator` qui requièrent un itérateur bidirectionnel ne doivent appeler aucune des fonctions membres `operator+=`, `operator+`, `operator-=`, `operator-` et `operator[]`, qui peuvent uniquement être utilisées avec des itérateurs d'accès aléatoire.  
  
 Si la plage d'un itérateur est \[`_First`, \_Last\), où le crochet de gauche indique l'inclusion de \_*First* et la parenthèse de droite indique l'inclusion des éléments jusqu'à \_*Left* tout en excluant \_*Left* lui\-même.  Les mêmes éléments sont inclus dans la séquence inversée \[**rev** – `_First`, **rev** – \_*Left*\) afin que si \_*Left* représente un élément après le dernier élément d'une séquence, le premier élément **rev** – \_*First* dans la séquence inversée pointe sur \*\(\_*Left* – 1\).  L'identité qui associe tous les itérateurs inverses à leurs itérateurs sous\-jacents est :  
  
 &\*\(**reverse\_iterator** \( *i* \) \) \=\= &\*\( *i* – 1\).  
  
 En pratique, cela signifie que dans la séquence inversée le reverse\_iterator se rapportera à l'élément situé une position au\-delà \(à droite\) de l'élément auquel l'itérateur se rapportait dans la séquence d'origine.  Ainsi, si un itérateur se rapportait à l'élément 6 dans la séquence \(2, 4, 6, 8\), le `reverse_iterator` se rapporte à l'élément 4 dans la séquence inversée \(8, 6, 4, 2\).  
  
### Constructeurs  
  
|||  
|-|-|  
|[reverse\_iterator](../Topic/reverse_iterator::reverse_iterator.md)|Construit un `reverse_iterator` par défaut ou un `reverse_iterator` à partir d'un itérateur sous\-jacent.|  
  
### Typedef  
  
|||  
|-|-|  
|[difference\_type](../Topic/reverse_iterator::difference_type.md)|Type qui fournit la différence entre deux objets `reverse_iterator` se rapportant à des éléments dans le même conteneur.|  
|[iterator\_type](../Topic/reverse_iterator::iterator_type.md)|Type qui fournit l'itérateur sous\-jacent d'un `reverse_iterator`.|  
|[pointer](../Topic/reverse_iterator::pointer.md)|Type qui fournit un pointeur vers un élément traité par un `reverse_iterator`.|  
|[référence](../Topic/reverse_iterator::reference.md)|Type qui fournit une référence à un élément traité par un `reverse_iterator`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[base](../Topic/reverse_iterator::base.md)|Récupère l'itérateur sous\-jacent à partir de son `reverse_iterator`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/reverse_iterator::operator*.md)|Retourne l'élément traité par `reverse_iterator`.|  
|[operator\+](../Topic/reverse_iterator::operator+.md)|Ajoute un décalage à un itérateur et retourne le nouvel `reverse_iterator` qui se rapporte à l'élément inséré à la nouvelle position décalée.|  
|[operator\+\+](../Topic/reverse_iterator::operator++.md)|Incrémente le `reverse_iterator` à l'élément suivant.|  
|[operator\+\=](../Topic/reverse_iterator::operator+=.md)|Ajoute un décalage spécifié à partir d'un `reverse_iterator`.|  
|[operator\-](../Topic/reverse_iterator::operator-.md)|Soustrait un décalage à un `reverse_iterator` et retourne un `reverse_iterator` se rapportant à l'élément situé à la position décalée.|  
|[operator\-\-](../Topic/reverse_iterator::operator--.md)|Décrémente le `reverse_iterator` à l'élément précédent.|  
|[operator\-\=](../Topic/reverse_iterator::operator-=.md)|Soustrait un décalage spécifié d'un `reverse_iterator`.|  
|[operator\-\>](../Topic/reverse_iterator::operator-%3E.md)|Retourne un pointeur vers l'élément traité par le `reverse_iterator`.|  
|[operator&#91;&#93;](../Topic/reverse_iterator::operator.md)|Retourne une référence à un élément décalé d'un nombre donné de positions par rapport à l'élément auquel un `reverse_iterator` se rapportait.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)