---
title: "basic_iostream, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istream/std::basic_iostream"
  - "std.basic_iostream"
  - "basic_iostream"
  - "std::basic_iostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_iostream (classe)"
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# basic_iostream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de flux qui peut effectuer à la fois l'entrée et la sortie.  
  
## Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_iostream : public basic_istream<Elem, Tr>,  
        public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr> *_Strbuf);  
    virtual ~basic_iostream();  
};  
```  
  
## Notes  
 La classe de modèle décrit un objet qui contrôle les insertions, via sa classe de base [basic\_ostream](../standard-library/basic-ostream-class.md)\<`Elem`, `Tr`\>, et les extractions, via sa classe de base [basic\_istream](../standard-library/basic-istream-class.md)\<`Elem`, `Tr`\>.  Les deux objets partagent une classe de base virtuelle commune [basic\_ios](../standard-library/basic-ios-class.md)\<`Elem`, `Tr`\>.  Ils gèrent également une mémoire tampon de flux commune, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.  Le constructeur initialise ses classes de base via `basic_istream`\(**strbuf**\) et `basic_ostream`\(**strbuf**\).  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_iostream](../Topic/basic_iostream::basic_iostream.md)|Créez un objet `basic_iostream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[swap](../Topic/basic_iostream::swap.md)|Échange le contenu de l'objet `basic_iostream` fourni avec le contenu de cet objet.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=](../Topic/basic_iostream::operator=.md)|Assigne la valeur d'un objet `basic_iostream` spécifié à cet objet.  Il s'agit d'une assignation de déplacement impliquant une `rvalue` qui ne laisse pas de copie.|  
  
## Configuration requise  
 **En\-tête :** \<istream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)