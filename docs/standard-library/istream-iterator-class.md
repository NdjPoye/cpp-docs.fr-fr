---
title: "istream_iterator, classe | Microsoft Docs"
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
  - "iterator/std::istream_iterator"
  - "std.istream_iterator"
  - "std::istream_iterator"
  - "istream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream_iterator (classe)"
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# istream_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet itérateur d'entrée.  Elle extrait des objets de classe `Type` d'un flux d'entrée, auquel elle accède via un objet qu'elle stocke, de type `pointer` vers `basic_istream`\<`CharType`, `Traits`\>.  
  
## Syntaxe  
  
```  
template<class Type,  
    class CharType = char,  
    class Traits = char_traits<CharType>,  
    class Distance = ptrdiff_t,  
> class istream_iterator  
 : public iterator<  
        input_iterator_tag,  
        Type,   
        Distance,   
        const Type *,  
        const Type&  
    >;  
```  
  
#### Paramètres  
 `Type`  
 Type de l'objet à extraire du flux d'entrée.  
  
 `CharType`  
 Type qui représente le type de caractère de `istream_iterator`.  Cet argument est facultatif et sa valeur par défaut est `char`.  
  
 `Traits`  
 Type qui représente le type de caractère de `istream_iterator`.  Cet argument est facultatif et sa valeur par défaut est `char_traits`\<`CharType`\>.  
  
 `Distance`  
 Type intégral signé qui représente le type de différence de `istream_iterator`.  Cet argument est facultatif et sa valeur par défaut est `ptrdiff_t`.  
  
 Après avoir construit ou incrémenté un objet de classe istream\_iterator avec un pointeur non null stocké, l'objet tente d'extraire et de stocker un objet de type `Type` à partir du flux d'entrée associé.  Si l'extraction échoue, l'objet remplace le pointeur stocké par un pointeur null, créant ainsi un indicateur de fin de séquence.  
  
### Constructeurs  
  
|||  
|-|-|  
|[istream\_iterator](../Topic/istream_iterator::istream_iterator.md)|Construit un itérateur de fin de flux comme `istream_iterator` par défaut ou un `istream_iterator` initialisé sur le type de flux de l'itérateur à partir duquel il lit.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/istream_iterator::char_type.md)|Type qui fournit le type de caractère de l'objet `istream_iterator`.|  
|[istream\_type](../Topic/istream_iterator::istream_type.md)|Type qui fournit le type de flux de `istream_iterator`.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|Type qui fournit le type de caractéristique de `istream_iterator`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/istream_iterator::operator*.md)|L'opérateur de déréférencement retourne l'objet stocké de type `Type` auquel se rapporte l'objet `istream_iterator`.|  
|[operator\-\>](../Topic/istream_iterator::operator-%3E.md)|Retourne la valeur d'un membre, le cas échéant.|  
|[operator\+\+](../Topic/istream_iterator::operator++.md)|Extrait un objet incrémenté du flux d'entrée ou copie l'objet avant de l'incrémenter et retourne la copie.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [input\_iterator\_tag, struct](../standard-library/input-iterator-tag-struct.md)   
 [iterator, struct](../standard-library/iterator-struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)