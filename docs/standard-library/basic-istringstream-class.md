---
title: "basic_istringstream, classe | Microsoft Docs"
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
  - "std::basic_istringstream"
  - "sstream/std::basic_istringstream"
  - "basic_istringstream"
  - "std.basic_istringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istringstream (classe)"
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_istringstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux de classe [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>.  
  
## Syntaxe  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### Paramètres  
 `Alloc`  
 Classe allocator.  
  
 `Elem`  
 Type de l'élément de base de la chaîne.  
  
 *Tr*  
 Caractéristique spécialisée sur l'élément de base de la chaîne.  
  
## Notes  
 La classe de modèle décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux de classe [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr**, et dont les éléments sont alloués par un allocateur de classe `Alloc`.  L'objet stocke un objet de classe basic\_stringbuf \<**Elem**, **Tr**, `Alloc`\>.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_istringstream](../Topic/basic_istringstream::basic_istringstream.md)|Construit un objet de type `basic_istringstream`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_istringstream::allocator_type.md)|Le type est un synonyme du paramètre de modèle `Alloc`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_istringstream::rdbuf.md)|Retourne l'adresse de la mémoire tampon de flux stockée de type `pointer` à [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem`, `Tr`, `Alloc`\>.|  
|[str](../Topic/basic_istringstream::str.md)|Obtient ou définit le texte dans une mémoire tampon de chaîne sans modifier la position d'écriture.|  
|[échange](../Topic/basic_istringstream::swap.md)|Échange les valeurs de cet objet `basic_istringstream` avec celles de l'objet fourni.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/basic_istringstream::operator=.md)|Assigne les valeurs à cet objet `basic_istringstream` à partir du paramètre d'objet.|  
  
## Configuration requise  
 **En\-tête :** \<sstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)