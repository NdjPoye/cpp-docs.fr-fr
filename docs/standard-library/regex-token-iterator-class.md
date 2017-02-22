---
title: "regex_token_iterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "regex_token_iterator"
  - "std.tr1.regex_token_iterator"
  - "std::tr1::regex_token_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_token_iterator (classe) (TR1)"
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# regex_token_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe d’itérateur pour les sous\-correspondances.  
  
## Syntaxe  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_token_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef sub_match<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const sub_match<BidIt> *pointer;  
    typedef const sub_match<BidIt>& reference;  
  
    regex_token_iterator();  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, int submatch = 0,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, const std::vector<int> submatches,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
    template<std::size_t N>  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, const int (&submatches)[N],  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_token_iterator& right);  
    bool operator!=(const regex_token_iterator& right);  
    const basic_string<Elem>& operator*();  
    const basic_string<Elem> *operator->();  
    regex_token_iterator& operator++();  
    regex_token_iterator& operator++(int);  
private:  
    regex_iterator<BidIt, Elem, RXtraits> it; // exposition only  
    vector<int> subs;                         // exposition only  
    int pos;                                  // exposition only  
    };  
```  
  
#### Paramètres  
 `BidIt`  
 Type d'itérateur pour les sous\-correspondances.  
  
 `Elem`  
 Type des éléments à faire correspondre.  
  
 `RXtraits`  
 Classe Traits des éléments.  
  
## Notes  
 Cette classe de modèle décrit un objet itérateur forward constant. D’un point de vue conceptuel, elle contient un objet `regex_iterator` utilisé pour la recherche d’expressions régulières dans une séquence de caractères. Elle extrait des objets de type `sub_match<BidIt>` représentant les sous\-correspondances identifiées par les valeurs d’index dans le vecteur stocké `subs` pour chaque correspondance d’expression régulière.  
  
 La valeur d’index \-1 désigne la séquence de caractères qui commence immédiatement après la fin de la correspondance d’expression régulière précédente, ou le début de la séquence de caractères en l’absence de correspondance d’expression régulière précédente. Par ailleurs, la séquence s’étend jusqu’au premier caractère \(sans l’inclure\) de la correspondance d’expression régulière actuelle, ou jusqu’à la fin de la séquence de caractères en l’absence de correspondance actuelle. Toute autre valeur d’index `idx` désigne le contenu du groupe de capture situé dans `it.match[idx]`.  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_token\_iterator](../standard-library/regex-token-iterator-class.md)   
 [regex\_iterator, classe](../standard-library/regex-iterator-class.md)