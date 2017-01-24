---
title: "basic_stringstream, classe | Microsoft Docs"
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
  - "std.basic_stringstream"
  - "basic_stringstream"
  - "std::basic_stringstream"
  - "sstream/std::basic_stringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_stringstream (classe)"
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_stringstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'insertion et l'extraction d'éléments et d'objets encodés à l'aide d'une mémoire tampon de flux de classe [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>.  
  
## Syntaxe  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_stringstream : public basic_iostream<Elem, Tr>  
```  
  
#### Paramètres  
 `Alloc`  
 Classe allocator.  
  
 `Elem`  
 Type de l'élément de base de la chaîne.  
  
 *Tr*  
 Caractéristique spécialisée sur l'élément de base de la chaîne.  
  
## Notes  
 La classe de modèle décrit un objet qui contrôle l'insertion et l'extraction d'éléments et d'objets encodés à l'aide d'une mémoire tampon de flux de classe [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr**, et dont les éléments sont alloués par un allocateur de classe `Alloc`.  L'objet stocke un objet de classe basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\>.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_stringstream](../Topic/basic_stringstream::basic_stringstream.md)|Construit un objet de type `basic_stringstream`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_stringstream::allocator_type.md)|Le type est un synonyme du paramètre de modèle `Alloc`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_stringstream::rdbuf.md)|Retourne l'adresse de la mémoire tampon de flux stockée de type `pointer` à [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem`, `Tr`, `Alloc`\>.|  
|[str](../Topic/basic_stringstream::str.md)|Obtient ou définit le texte dans une mémoire tampon de chaîne sans modifier la position d'écriture.|  
  
## Configuration requise  
 **En\-tête :** \<sstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)