---
title: "basic_stringbuf, classe | Microsoft Docs"
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
  - "basic_stringbuf"
  - "sstream/std::basic_stringbuf"
  - "std.basic_stringbuf"
  - "std::basic_stringbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_stringbuf (classe)"
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: 28
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_stringbuf, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`, vers et à partir d'une séquence d'éléments stockés dans un objet de tableau.  
  
## Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### Paramètres  
 `Alloc`  
 Classe allocator.  
  
 `Elem`  
 Type de l'élément de base de la chaîne.  
  
 `Tr`  
 Caractéristique spécialisée sur l'élément de base de la chaîne.  
  
## Notes  
 L'objet est alloué, étendu et libéré en fonction des modifications apportées à la séquence.  
  
 Un objet de classe basic\_stringbuf \<`Elem`, `Tr`, `Alloc`\> stocke une copie de l'argument `ios_base::`[openmode](../Topic/ios_base::openmode.md) de son constructeur en tant que **mode**`stringbuf` :  
  
-   Si `mode & ios_base::in` est différent de zéro, la mémoire tampon d'entrée est accessible. Pour plus d'informations, consultez [basic\_streambuf, classe](../standard-library/basic-streambuf-class.md).  
  
-   Si `mode & ios_base::out` est différent de zéro, la mémoire tampon de sortie est accessible.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_stringbuf](../Topic/basic_stringbuf::basic_stringbuf.md)|Construit un objet de type `basic_stringbuf`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_stringbuf::allocator_type.md)|Le type est un synonyme du paramètre de modèle `Alloc`.|  
|[char\_type](../Topic/basic_stringbuf::char_type.md)|Associe un nom de type au paramètre de modèle `Elem`.|  
|[int\_type](../Topic/basic_stringbuf::int_type.md)|Rend ce type dans la portée de `basic_filebuf` équivalent au type du même nom dans la portée de `Tr`.|  
|[off\_type](../Topic/basic_stringbuf::off_type.md)|Rend ce type dans la portée de `basic_filebuf` équivalent au type du même nom dans la portée de `Tr`.|  
|[pos\_type](../Topic/basic_stringbuf::pos_type.md)|Rend ce type dans la portée de `basic_filebuf` équivalent au type du même nom dans la portée de `Tr`.|  
|[traits\_type](../Topic/basic_stringbuf::traits_type.md)|Associe un nom de type au paramètre de modèle `Tr`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[dépassement de capacité](../Topic/basic_stringbuf::overflow.md)|Fonction virtuelle protégée qui peut être appelée quand un nouveau caractère est inséré dans une mémoire tampon saturée.|  
|[pbackfail](../Topic/basic_stringbuf::pbackfail.md)|La fonction membre virtuelle protégée tente de remettre un élément dans la mémoire tampon d'entrée, puis en fait l'élément actif \(vers lequel pointe le pointeur suivant\).|  
|[seekoff](../Topic/basic_stringbuf::seekoff.md)|La fonction membre virtuelle protégée tente de modifier les positions actuelles des flux contrôlés.|  
|[seekpos](../Topic/basic_stringbuf::seekpos.md)|La fonction membre virtuelle protégée tente de modifier les positions actuelles des flux contrôlés.|  
|[str](../Topic/basic_stringbuf::str.md)|Obtient ou définit le texte dans une mémoire tampon de chaîne sans modifier la position d'écriture.|  
|swap||  
|[underflow](../Topic/basic_stringbuf::underflow.md)|Fonction membre virtuelle protégée pour extraire l'élément actif du flux d'entrée.|  
  
## Configuration requise  
 **En\-tête :** \<sstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)