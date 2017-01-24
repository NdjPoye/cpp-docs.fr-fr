---
title: "ostream_iterator, classe | Microsoft Docs"
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
  - "ostream_iterator"
  - "std.ostream_iterator"
  - "std::ostream_iterator"
  - "iterator/std::ostream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream_iterator (classe)"
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ostream_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle ostream\_iterator décrit un objet itérateur de sortie qui enregistre les éléments consécutifs dans le flux de sortie avec l'**opérateur \<\<** d'extraction.  
  
## Syntaxe  
  
```  
  
      template <  
   class Type   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
class ostream_iterator  
```  
  
#### Paramètres  
 *Type*  
 Type d'objet à insérer dans le flux de sortie.  
  
 `CharType`  
 Type qui représente le type de caractère de `ostream_iterator`.  Cet argument est facultatif et sa valeur par défaut est `char`*.*  
  
 `Traits`  
 Type qui représente le type de caractère de `ostream_iterator`.  Cet argument est facultatif et sa valeur par défaut est `char_traits`\<*CharType\>.*  
  
 La classe ostream\_iterator doit répondre aux exigences d'un itérateur de sortie.  Les algorithmes peuvent être enregistrés directement dans le flux de sortie à l'aide de `ostream_iterator`.  
  
### Constructeurs  
  
|||  
|-|-|  
|[ostream\_iterator](../Topic/ostream_iterator::ostream_iterator.md)|Construit un `ostream_iterator` qui est initialisé et délimité en vue de son enregistrement dans le flux de sortie.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/ostream_iterator::char_type.md)|Type qui fournit le type de caractère de `ostream_iterator`.|  
|[ostream\_type](../Topic/ostream_iterator::ostream_type.md)|Type qui fournit le type de flux de `ostream_iterator`.|  
|[traits\_type](../Topic/ostream_iterator::traits_type.md)|Type qui fournit le type de caractéristique de `ostream_iterator`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/ostream_iterator::operator*.md)|Opérateur de suppression de référence utilisé pour implémenter l'expression d'itérateur de sortie \*`i` \= `x`.|  
|[operator\+\+](../Topic/ostream_iterator::operator++.md)|Opérateur d'incrément non fonctionnel qui retourne un `ostream_iterator` au même objet qu'il a traité avant que l'opération n'ait été appelée.|  
|[operator\=](../Topic/ostream_iterator::operator=.md)|Opérateur d'assignation utilisé pour implémenter l'expression d'itérateur de sortie \*`i` \= `x` en vue d'un enregistrement dans le flux de sortie.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)