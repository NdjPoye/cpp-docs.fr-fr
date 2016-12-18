---
title: "istreambuf_iterator, classe | Microsoft Docs"
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
  - "istreambuf_iterator"
  - "std.istreambuf_iterator"
  - "std::istreambuf_iterator"
  - "streambuf/std::istreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istreambuf_iterator (classe)"
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
caps.latest.revision: 19
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# istreambuf_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle istreambuf\_iterator décrit un objet d'itérateur d'entrée qui extrait des éléments de caractères depuis un tampon de flux d'entrée, auquel il accède via un objet qu'il enregistre, du pointeur de type vers `basic_streambuf`\<**CharType**, **Traits**\>.  
  
## Syntaxe  
  
```  
  
      template <   
   class CharType  
   class Traits = char_traits<CharType>  
>  
class istreambuf_iterator  
: public iterator<input_iterator_tag, CharType, typename Traits::off_type, CharType *, CharType&>  
```  
  
#### Paramètres  
 `CharType`  
 Type qui représente le type de caractère pour istreambuf\_iterator.  
  
 `Traits`  
 Type qui représente le type de caractère pour istreambuf\_iterator.  Cet argument est facultatif et sa valeur par défaut est `char_traits`\<*CharType\>.*  
  
## Notes  
 La classe istreambuf\_iterator doit répondre aux exigences d'un itérateur d'entrée.  
  
 Après avoir construit ou incrémenté un objet de la classe istreambuf\_iterator avec un pointeur non null stocké, l'objet tente d'extraire et de stocker un objet de type **CharType** à partir du flux d'entrée associé.  Toutefois, l'extraction peut être différée jusqu'à ce que l'objet soit déréférencé ou copié.  Si l'extraction échoue, l'objet remplace le pointeur stocké par un pointeur null, créant ainsi un indicateur de fin de séquence.  
  
### Constructeurs  
  
|||  
|-|-|  
|[istreambuf\_iterator](../Topic/istreambuf_iterator::istreambuf_iterator.md)|Construit un `istreambuf_iterator` qui est initialisé pour lire des caractères à partir du flux d'entrée.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/istreambuf_iterator::char_type.md)|Type qui fournit le type de caractère de `ostreambuf_iterator`.|  
|[int\_type](../Topic/istreambuf_iterator::int_type.md)|Type qui fournit un type entier pour un `istreambuf_iterator`.|  
|[istream\_type](../Topic/istreambuf_iterator::istream_type.md)|Type qui fournit le type de flux de `istream_iterator`.|  
|[streambuf\_type](../Topic/istreambuf_iterator::streambuf_type.md)|Type qui fournit le type de flux de `istreambuf_iterator`.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|Type qui fournit le type de caractéristique de `istream_iterator`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[equal](../Topic/istreambuf_iterator::equal.md)|Vérifie l'égalité de deux itérateurs de tampon de flux d'entrée.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/istreambuf_iterator::operator*.md)|L'opérateur de suppression de référence retourne le caractère suivant du flux.|  
|[operator\+\+](../Topic/istreambuf_iterator::operator++.md)|Retourne le caractère suivant du flux d'entrée ou copie l'objet avant de l'incrémenter et de retourner sa copie.|  
|[operator\-\>](../Topic/istreambuf_iterator::operator-%3E.md)|Retourne la valeur d'un membre, le cas échéant.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [iterator, struct](../standard-library/iterator-struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)