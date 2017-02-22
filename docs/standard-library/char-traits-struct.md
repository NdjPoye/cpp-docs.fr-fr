---
title: "char_traits, struct | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::char_traits"
  - "std.char_traits"
  - "iosfwd/std::char_traits"
  - "char_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits (classe)"
  - "char_traits (struct)"
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# char_traits, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La structure char\_traits décrit les attributs associés à un caractère.  
  
## Syntaxe  
  
```  
template <  
   class CharType  
> struct char_traits;  
```  
  
#### Paramètres  
 `CharType`  
 Type de données de l'élément.  
  
## Notes  
 Le modèle de structure décrit différentes caractéristiques des caractères pour le type **CharType**.  La classe de modèle [basic\_string](../standard-library/basic-string-class.md) ainsi que plusieurs classes de modèle iostream, notamment [basic\_ios](../standard-library/basic-ios-class.md), utilisent ces informations pour manipuler les éléments de type **CharType**.  Un tel type d'élément ne doit pas requérir une construction ou une destruction explicite.  Il doit fournir un constructeur par défaut, un constructeur de copie et un opérateur d'affectation avec la sémantique attendue.  Une copie au niveau du bit doit avoir le même effet qu'une affectation.  Aucune des fonctions membres de la structure char\_traits ne peut lever des exceptions.  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/char_traits::char_type.md)|Type de caractère.|  
|[int\_type](../Topic/char_traits::int_type.md)|Type entier qui peut représenter un caractère de type `char_type` ou un caractère de fin de fichier \(EOF\).|  
|[off\_type](../Topic/char_traits::off_type.md)|Type entier qui peut représenter des décalages entre les positions dans un flux.|  
|[pos\_type](../Topic/char_traits::pos_type.md)|Type entier qui peut représenter des positions dans un flux.|  
|[state\_type](../Topic/char_traits::state_type.md)|Type qui représente l'état de la conversion de caractères multi\-octets dans un flux.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[assign](../Topic/char_traits::assign.md)|Affecte la valeur d'un caractère à un autre.|  
|[compare](../Topic/char_traits::compare.md)|Compare un nombre spécifié de caractères dans deux chaînes.|  
|[copy](../Topic/char_traits::copy.md)|Copie un nombre spécifié de caractères d'une chaîne vers une autre.  Obsolète.  Utilisez à la place [char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md).|  
|[\_Copy\_s](../Topic/char_traits::_Copy_s.md)|Copie un nombre spécifié de caractères d'une chaîne vers une autre.|  
|[eof](../Topic/char_traits::eof.md)|Retourne le caractère de fin de fichier \(EOF\).|  
|[eq](../Topic/char_traits::eq.md)|Teste si deux caractères `char_type` sont égaux.|  
|[eq\_int\_type](../Topic/char_traits::eq_int_type.md)|Teste si deux caractères représentés comme `int_type` sont égaux.|  
|[find](../Topic/char_traits::find.md)|Recherche la première occurrence d'un caractère spécifié dans une plage de caractères.|  
|[length](../Topic/char_traits::length.md)|Retourne la longueur d'une chaîne.|  
|[lt](../Topic/char_traits::lt.md)|Teste si un caractère est inférieur à un autre.|  
|[move](../Topic/char_traits::move.md)|Copie un nombre spécifié de caractères d'une séquence vers une autre séquence qui la chevauche éventuellement.  Obsolète.  Utilisez à la place [char\_traits::\_Move\_s](../Topic/char_traits::_Move_s.md).|  
|[\_Move\_s](../Topic/char_traits::_Move_s.md)|Copie un nombre spécifié de caractères d'une séquence vers une autre séquence qui la chevauche éventuellement.|  
|[not\_eof](../Topic/char_traits::not_eof.md)|Teste si un caractère est le caractère de fin de fichier \(EOF\).|  
|[to\_char\_type](../Topic/char_traits::to_char_type.md)|Convertit un caractère `int_type` en caractère `char_type` correspondant et retourne le résultat.|  
|[to\_int\_type](../Topic/char_traits::to_int_type.md)|Convertit un caractère `char_type` en caractère `int_type` correspondant et retourne le résultat.|  
  
## Configuration requise  
 **En\-tête :** \<string\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)