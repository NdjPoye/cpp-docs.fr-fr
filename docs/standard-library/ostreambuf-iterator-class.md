---
title: "ostreambuf_iterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.ostreambuf_iterator"
  - "streambuf/std::ostreambuf_iterator"
  - "ostreambuf_iterator"
  - "std::ostreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostreambuf_iterator (classe)"
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ostreambuf_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle ostreambuf\_iterator décrit un objet itérateur de sortie qui enregistre les éléments de caractères consécutifs dans le flux de sortie avec l'**opérateur\>\>** d'extraction.  Les objets `ostreambuf_iterator` diffèrent de ceux de la [classe ostream\_iterator](../standard-library/ostream-iterator-class.md) en présentant des caractères à la place d'un type générique dans le type d'objet inséré dans le flux de sortie.  
  
## Syntaxe  
  
```  
  
      template <   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
```  
  
#### Paramètres  
 `CharType`  
 Type qui représente le type de caractère pour l'objet ostreambuf\_iterator.  Cet argument est facultatif et sa valeur par défaut est `char`*.*  
  
 `Traits`  
 Type qui représente le type de caractère pour l'objet ostreambuf\_iterator.  Cet argument est facultatif et sa valeur par défaut est `char_traits`\<*CharType\>.*  
  
## Notes  
 La classe ostreambuf\_iterator doit être conforme aux spécifications d'un itérateur de sortie.  Les algorithmes peuvent être enregistrés directement dans le flux de sortie à l'aide d'un objet `ostreambuf_iterator`.  La classe fournit un itérateur de flux de bas niveau qui permet l'accès au flux d'E\/S brut \(sans mise en forme\) sous la forme de caractères et permet de contourner la mise en mémoire tampon et les traductions de caractères associées aux itérateurs de flux de haut niveau.  
  
### Constructeurs  
  
|||  
|-|-|  
|[ostreambuf\_iterator](../Topic/ostreambuf_iterator::ostreambuf_iterator.md)|Construit un objet `ostreambuf_iterator` initialisé pour enregistrer des caractères dans le flux de sortie.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/ostreambuf_iterator::char_type.md)|Type qui fournit le type de caractère de `ostreambuf_iterator`.|  
|[ostream\_type](../Topic/ostreambuf_iterator::ostream_type.md)|Type qui fournit le type de flux de `ostream_iterator`.|  
|[streambuf\_type](../Topic/ostreambuf_iterator::streambuf_type.md)|Type qui fournit le type de flux de l'objet `ostreambuf_iterator`.|  
|[traits\_type](../Topic/ostreambuf_iterator::traits_type.md)|Type qui fournit le type de caractéristique de `ostream_iterator`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[failed](../Topic/ostreambuf_iterator::failed.md)|Teste l'échec d'une insertion dans la mémoire tampon du flux de sortie.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/ostreambuf_iterator::operator*.md)|Opérateur de suppression de référence utilisé pour implémenter l'expression d'itérateur de sortie \*`i` \= `x`.|  
|[operator\+\+](../Topic/ostreambuf_iterator::operator++.md)|Opérateur d'incrément non fonctionnel qui retourne un `ostreambuf_iterator` au même objet qu'il a traité avant que l'opération n'ait été appelée.|  
|[operator\=](../Topic/ostreambuf_iterator::operator=.md)|L'opérateur insère un caractère dans la mémoire tampon du flux associé.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)