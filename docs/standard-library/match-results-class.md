---
title: "match_results, classe | Microsoft Docs"
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
  - "std.tr1.match_results"
  - "match_results"
  - "std::tr1::match_results"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "match_results (classe) (TR1)"
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
caps.latest.revision: 16
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# match_results, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contient une séquence de sous\-correspondances.  
  
## Syntaxe  
  
```  
template<class BidIt,  
    class Alloc = allocator<typename iterator_traits<BidIt>::value_type> >  
    class match_results {  
public:  
    explicit match_results(const Alloc& alloc = Alloc());  
    match_results(const match_results& right);  
  
    match_results& operator=(const match_results& right);  
  
    difference_type position(size_type sub = 0) const;  
    difference_type length(size_type sub = 0) const;  
    string_type str(size_type sub = 0) const;  
    const_reference operator[](size_type n) const;  
  
    const_reference prefix() const;  
    const_reference suffix() const;  
    const_iterator begin() const;  
    const_iterator end() const;  
  
    template<class OutIt>  
        OutIt format(OutIt out,  
            const string_type& fmt, match_flag_type flags = format_default) const;  
    string_type format(const string_type& fmt,  
        match_flag_type flags = format_default) const;  
  
    allocator_type get_allocator() const;  
    void swap(const match_results& other) throw();  
  
    size_type size() const;  
    size_type max_size() const;  
    bool empty() const;  
  
    typedef sub_match<BidIt> value_type;  
    typedef const typename Alloc::const_reference const_reference;  
    typedef const_reference reference;  
    typedef T0 const_iterator;  
    typedef const_iterator iterator;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef typename Alloc::size_type size_type;  
    typedef Alloc allocator_type;  
    typedef typename iterator_traits<BidIt>::value_type char_type;  
    typedef basic_string<char_type> string_type;  
    };  
```  
  
#### Paramètres  
 `BidIt`  
 Type d'itérateur pour les sous\-correspondances.  
  
 `Alloc`  
 Type d'un allocateur pour la gestion du stockage.  
  
## Notes  
 La classe de modèle décrit un objet qui contrôle une séquence non modifiable d’éléments de type `sub_match<BidIt>`, générés par une recherche d’expression régulière. Chaque élément pointe vers la sous\-séquence qui correspond au groupe de capture correspondant à cet élément.  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)