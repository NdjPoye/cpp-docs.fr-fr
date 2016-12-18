---
title: "&lt;sstream&gt; | Microsoft Docs"
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
  - "std.<sstream>"
  - "std::<sstream>"
  - "<sstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sstream (en-tête)"
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 20
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;sstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs classes de modèle qui prennent en charge des opérations d'iostreams sur les séquences stockées dans un objet tableau alloué.  De telles séquences sont immédiatement converties en objets de classe de modèle [basic\_string](../standard-library/basic-string-class.md).  
  
## Syntaxe  
  
```  
namespace std {  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringbuf;  
typedef basic_stringbuf<char> stringbuf;  
typedef basic_stringbuf<wchar_t> wstringbuf;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_istringstream;  
typedef basic_istringstream<char> istringstream;  
typedef basic_istringstream<wchar_t> wistringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_ostringstream;  
typedef basic_ostringstream<char> ostringstream;  
typedef basic_ostringstream<wchar_t> wostringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringstream;  
typedef basic_stringstream<char> stringstream;  
typedef basic_stringstream<wchar_t> wstringstream;  
  
        // TEMPLATE FUNCTIONS  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_stringbuf<CharType, Traits, Allocator>& _Left,  
        basic_stringbuf<CharType, Traits, Allocator>& _Right  
    );   
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_istringstream<CharType, Traits, Allocator>& _Left,  
        basic_istringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_ostringstream<CharType, Traits, Allocator>& _Left,  
        basic_ostringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap (  
        basic_stringstream<CharType, Traits, Allocator>& _Left,  
        basic_stringstream<CharType, Traits, Allocator>& _Right  
    );  
}  // namespace std  
  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Left`|Référence à un objet `sstream`.|  
|`_Right`|Référence à un objet `sstream`.|  
  
## Notes  
 Les objets de type `char *` peuvent utiliser la fonctionnalité dans [\<strstream\>](../standard-library/strstream.md) pour transmettre un flux.  Toutefois, `<strstream>` est déconseillé et l'utilisation d'`<sstream>` est conseillée.  
  
### Typedef  
  
|||  
|-|-|  
|[istringstream](../Topic/istringstream.md)|Crée un type `basic_istringstream` spécialisé sur un paramètre de modèle `char`.|  
|[ostringstream](../Topic/ostringstream.md)|Crée un type `basic_ostringstream` spécialisé sur un paramètre de modèle `char`.|  
|[stringbuf](../Topic/stringbuf.md)|Crée un type `basic_stringbuf` spécialisé sur un paramètre de modèle `char`.|  
|[stringstream](../Topic/stringstream.md)|Crée un type `basic_stringstream` spécialisé sur un paramètre de modèle `char`.|  
|[wistringstream](../Topic/wistringstream.md)|Crée un type `basic_istringstream` spécialisé sur un paramètre de modèle `wchar_t`.|  
|[wostringstream](../Topic/wostringstream.md)|Crée un type `basic_ostringstream` spécialisé sur un paramètre de modèle `wchar_t`.|  
|[wstringbuf](../Topic/wstringbuf.md)|Crée un type `basic_stringbuf` spécialisé sur un paramètre de modèle `wchar_t`.|  
|[wstringstream](../Topic/wstringstream.md)|Crée un type `basic_stringstream` spécialisé sur un paramètre de modèle `wchar_t`.|  
  
### Manipulateurs  
  
|||  
|-|-|  
|[échange](../Topic/%3Csstream%3E%20swap.md)|Échanger des valeurs entre deux objets `sstream`.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_stringbuf](../standard-library/basic-stringbuf-class.md)|Décrit une mémoire tampon du flux qui contrôle la transmission des éléments de type **Elem**, dont les caractéristiques de caractères sont déterminées par la classe **Tr**, vers et depuis une séquence d'éléments stockés dans un tableau.|  
|[basic\_istringstream](../standard-library/basic-istringstream-class.md)|Décrit un objet qui contrôle l'extraction des éléments et des objets encodés d'une mémoire tampon du flux de classe  [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, avec des éléments du type **Elem**, dont les caractéristiques de caractères sont déterminées par la classe **Tr**, et dont les éléments sont alloués par un allocateur de la classe `Alloc`.|  
|[basic\_ostringstream](../standard-library/basic-ostringstream-class.md)|Décrit un objet qui contrôle l'insertion des éléments et des objets encodés dans une mémoire tampon du flux de classe  [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, avec des éléments du type **Elem**, dont les caractéristiques de caractères sont déterminées par la classe **Tr**, et dont les éléments sont alloués par un allocateur de la classe `Alloc`.|  
|[basic\_stringstream](../standard-library/basic-stringstream-class.md)|Décrit un objet qui contrôle l'insertion et l'extraction des éléments et des objets encodés utilisant une mémoire tampon de flux de classe  [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, avec des éléments du type **Elem**, dont les caractéristiques de caractères sont déterminées par la classe **Tr**, et dont les éléments sont alloués par un allocateur de la classe `Alloc`.|  
  
## Configuration requise  
  
-   **En\-tête :** \<sstream\>  
  
-   **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)