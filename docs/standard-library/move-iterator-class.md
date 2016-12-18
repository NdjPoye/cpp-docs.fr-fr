---
title: "move_iterator, classe | Microsoft Docs"
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
  - "std.move_iterator"
  - "move_iterator"
  - "iterator/std::move_iterator"
  - "std::move_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "move_iterator (classe)"
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# move_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le modèle de classe `move_iterator` est un wrapper pour un itérateur.  Le move\_iterator fournit le même comportement que l'itérateur qu'il encapsule \(ou stocke\), à la différence près qu'il convertit l'opérateur de déréférence de l'itérateur stocké en une référence rvalue, convertissant ainsi une copie en déplacement.  Pour plus d'informations sur les rvalues, consultez [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Syntaxe  
  
```  
template<class Iterator>  
    class move_iterator {  
public:  
    typedef Iterator iterator_type;  
    typedef typename      
        iterator_traits<Iterator>::iterator_category  
            iterator_category;  
    typedef typename iterator_traits<Iterator>::value_type  
        value_type;  
    typedef typename iterator_traits<Iterator>::difference_type  
        difference_type;  
    typedef Iterator  
        pointer;  
    typedef value_type&&  
        reference;  
  
    move_iterator();  
    explicit move_iterator (Iterator right);  
    template<class Type>  
        move_iterator (const move_iterator<Type>& right);  
    template <class Type>   
        move_iterator& operator=(const move_iterator<Type>& right);  
  
    iterator_type base () const;  
    reference operator* () const;  
    pointer operator-> () const;  
  
    move_iterator& operator++ ();  
    move_iterator operator++ (int);  
    move_iterator& operator-- ();  
    move_iterator operator-- (int);  
  
    move_iterator& operator+= (difference_type off);  
    move_iterator operator+ (difference_type off) const;  
    move_iterator& operator-= (difference_type off);  
    move_iterator operator- (difference_type off) const;  
    reference operator[] (difference_type off) const;  
    };  
```  
  
## Notes  
 La classe de modèle décrit un objet qui se comporte comme un itérateur, sauf lorsqu'il est déréférencé.  Elle stocke un itérateur d'accès aléatoire de type `Iterator`, accessible via la fonction membre `base``()`.  Toutes les opérations effectuées sur un `move_iterator` sont exécutées directement sur l'itérateur stocké, mais le résultat du `operator*` est implicitement converti en `value_type&&` pour créer une référence rvalue.  
  
 Un `move_iterator` peut être capable d'effectuer des opérations qui ne sont pas définies par l'itérateur encapsulé.  Ces opérations ne doivent pas être utilisées.  
  
### Constructeurs  
  
|||  
|-|-|  
|[move\_iterator](../Topic/move_iterator::move_iterator.md)|Constructeur des objets de type `move_iterator`.|  
  
### Typedef  
  
|||  
|-|-|  
|[move\_iterator::iterator\_type](../Topic/move_iterator::iterator_type.md)|Synonyme pour le paramètre du modèle `RandomIterator`.|  
|[move\_iterator::iterator\_category](../Topic/move_iterator::iterator_category.md)|Synonyme d'une expression `typename` plus longue du même nom, `iterator_category` représente les fonctionnalités générales de l'itérateur.|  
|[move\_iterator::value\_type](../Topic/move_iterator::value_type.md)|Synonyme d'une expression `typename` plus longue du même nom, `value_type` décrit le type des éléments de l'itérateur.|  
|[move\_iterator::difference\_type](../Topic/move_iterator::difference_type.md)|Synonyme d'une expression `typename` plus longue du même nom, `difference_type` décrit le type intégral requis pour exprimer des différences de valeur entre les éléments.|  
|[move\_iterator::pointer](../Topic/move_iterator::pointer.md)|Synonyme du paramètre de modèle `RandomIterator`.|  
|[move\_iterator::reference](../Topic/move_iterator::reference.md)|Synonyme de la référence `rvalue` `value_type&&`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[move\_iterator::base](../Topic/move_iterator::base.md)|La fonction membre retourne l'itérateur stocké encapsulé par le `move_iterator`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[move\_iterator::operator\*](../Topic/move_iterator::operator*.md)|Retourne `(reference)*``base``().`.|  
|[move\_iterator::operator\+\+](../Topic/move_iterator::operator++.md)|Incrémente l'itérateur stocké.  Le comportement exact varie selon qu'il s'agit d'une préincrémentation ou d'une postincrémentation.|  
|[move\_iterator::operator\-\-](../Topic/move_iterator::operator--.md)|Décrémente l'itérateur stocké.  Le comportement exact varie selon qu'il s'agit d'une préincrémentation ou d'une postincrémentation.|  
|[move\_iterator::operator\-\>](../Topic/move_iterator::operator-%3E.md)|Retourne `&**this`.|  
|[move\_iterator::operator\-](../Topic/move_iterator::operator-.md)|Retourne `move_iterator(*this) -=` en soustrayant d'abord la valeur située à droite de la position actuelle.|  
|[move\_iterator::operator](../Topic/move_iterator::operator.md)|Retourne `(reference)*(*this + off)`.  Permet de spécifier un décalage depuis la base actuelle pour obtenir la valeur de l'emplacement.|  
|[move\_iterator::operator\+](../Topic/move_iterator::operator+.md)|Retourne la valeur `move_iterator(*this) +=` .  Permet d'ajouter un décalage à la base pour obtenir la valeur de l'emplacement.|  
|[move\_iterator::operator\+\=](../Topic/move_iterator::operator+=.md)|Ajoute la valeur située à droite de l'itérateur stocké, et retourne `*this`.|  
|[move\_iterator::operator\-\=](../Topic/move_iterator::operator-=.md)|Soustrait la valeur située à droite de l'itérateur stocké, et retourne `*this`.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)   
 [Constructeurs de déplacement et opérateurs d'assignation de déplacement \(C\+\+\)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)