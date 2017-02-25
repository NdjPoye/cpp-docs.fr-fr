---
title: "bitset, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bitset/std::bitset"
  - "std::bitset"
  - "std.bitset"
  - "bitset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitset (classe)"
ms.assetid: 28b86964-87b4-429c-8124-b6c251b6c50b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# bitset, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un type d'objet stockant une séquence composée d'un nombre fixe de bits qui offrent un moyen compact de conserver des indicateurs d'un ensemble d'éléments ou de conditions.  La classe bitset prend en charge les opérations sur les objets de type bitset qui contiennent une collection de bits et qui fournissent un accès à délai constant à chaque bit.  
  
## Syntaxe  
  
```  
  
     template <size_t   
     N  
     >  
class bitset  
```  
  
#### Paramètres  
 *N*  
 Spécifie le nombre de bits dans l'objet bitset avec un entier différent de zéro de type **size\_t** qui doit être connu au moment de la compilation.  
  
## Notes  
 Contrairement à la [classe vector\<bool\>](../standard-library/vector-bool-class.md) similaire, la classe bitset n'a pas d'itérateurs et n'est pas un conteneur STL.  Elle diffère également de vector\<bool\> par sa taille spécifique qui est déterminée au moment de la compilation en fonction de la taille spécifiée par le paramètre de modèle **N** quand **bitset\<N\>** est déclaré.  
  
 Un bit est défini si sa valeur est 1, et est réinitialisé si sa valeur est 0.  Basculer un bit consiste à changer sa valeur de 1 en 0, ou de 0 en 1.  Les **N** bits d'un bitset sont indexés par des valeurs entières allant de 0 à **N** \- 1, où 0 indexe la position du premier bit et **N**\- 1 la position du bit final.  
  
### Constructeurs  
  
|||  
|-|-|  
|[bitset](../Topic/bitset::bitset.md)|Construit un objet de la classe `bitset<N>` et initialise les bits à zéro, à une valeur spécifiée ou à des valeurs obtenues auprès des caractères d'une chaîne.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/bitset::element_type.md)|Type qui est un synonyme du type de données `bool` et qui peut être utilisé pour référencer les bits des éléments d'un `bitset`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[toutes les](../Topic/bitset::all.md)|Teste tous les bits de ce `bitset` pour déterminer s'ils sont tous définis sur `true`.|  
|[any](../Topic/bitset::any.md)|La fonction membre teste si des bits de la séquence sont définis sur 1.|  
|[count](../Topic/bitset::count.md)|La fonction membre retourne le nombre de bits définis dans la séquence de bits.|  
|[flip](../Topic/bitset::flip.md)|Bascule la valeur de tous les bits d'un `bitset` ou bascule la valeur d'un seul bit à une position spécifiée.|  
|[none](../Topic/bitset::none.md)|Teste si aucun bit n'a été défini sur 1 dans un objet `bitset`.|  
|[reset](../Topic/bitset::reset.md)|Réinitialise tous les bits d'un `bitset` à 0 ou réinitialise à 0 un bit à une position spécifiée.|  
|[set](../Topic/bitset::set.md)|Définit tous les bits d'un `bitset` sur 1 ou définit sur 1 un bit à une position spécifiée.|  
|[size](../Topic/bitset::size.md)|Retourne le nombre de bits d'un objet `bitset`.|  
|[test](../Topic/bitset::test.md)|Teste si le bit à une position spécifiée d'un `bitset` est défini sur 1.|  
|[to\_string](../Topic/bitset::to_string.md)|Convertit un objet `bitset` en une représentation sous forme de chaîne.|  
|[to\_ullong](../Topic/bitset::to_ullong.md)|Retourne la somme des valeurs des bits d'un `bitset` sous forme de `unsigned long long`.|  
|[to\_ulong](../Topic/bitset::to_ulong.md)|Convertit un objet `bitset` en un `unsigned long` qui générerait la séquence de bits contenue s'il était utilisé pour initialiser le `bitset`.|  
  
### Classes membres  
  
|||  
|-|-|  
|[reference](../Topic/bitset::reference.md)|Classe proxy qui fournit des références aux bits contenus dans un `bitset` et qui est utilisée pour accéder aux bits individuels et pour s'en servir comme une classe d'assistance pour l'opérateur `operator[]` de la classe `bitset`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\!\=](../Topic/bitset::operator!=.md)|Teste l'inégalité d'un `bitset` cible avec un `bitset` spécifié.|  
|[operator&\=](../Topic/bitset::operator&=.md)|Effectue une combinaison au niveau du bit de bitsets avec l'opération `AND` logique.|  
|[operator\<\<](../Topic/bitset::operator%3C%3C.md)|Décale les bits d'un `bitset` vers la gauche d'un nombre spécifié de positions et retourne le résultat dans un nouveau `bitset`.|  
|[operator\<\<\=](../Topic/bitset::operator%3C%3C=.md)|Décale les bits d'un `bitset` vers la gauche d'un nombre spécifié de positions et retourne le résultat dans le `bitset` ciblé.|  
|[operator\=\=](../Topic/bitset::operator==.md)|Teste l'égalité d'un `bitset` cible avec un `bitset` spécifié.|  
|[operator\>\>](../Topic/bitset::operator%3E%3E.md)|Décale les bits d'un `bitset` vers la droite d'un nombre spécifié de positions et retourne le résultat dans un nouveau `bitset`.|  
|[operator\>\>\=](../Topic/bitset::operator%3E%3E=.md)|Décale les bits d'un `bitset` vers la droite d'un nombre spécifié de positions et retourne le résultat dans le `bitset` ciblé.|  
|[operator&#91;&#93;](../Topic/bitset::operator.md)|Retourne une référence à un bit à une position spécifiée d'un `bitset` si le `bitset` est modifiable ; sinon, retourne la valeur du bit à cette position.|  
|[operator^\=](../Topic/bitset::operator%5E=.md)|Effectue une combinaison au niveau du bit de bitsets avec l'opération `OR` exclusive.|  
|[operator&#124;\=](../Topic/bitset::operator%7C=.md)|Effectue une combinaison au niveau du bit de bitsets avec l'opération `OR` inclusive.|  
|[operator~](../Topic/bitset::operator~.md)|Bascule la valeur de tous les bits d'un `bitset` cible et retourne le résultat.|  
  
## Configuration requise  
 **En\-tête :** \<bitset\>  
  
 **Espace de noms :** std