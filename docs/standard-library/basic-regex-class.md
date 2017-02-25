---
title: "basic_regex, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::basic_regex"
  - "basic_regex"
  - "std.tr1.basic_regex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_regex (classe) (TR1)"
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# basic_regex, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule une expression régulière.  
  
## Syntaxe  
  
```  
template<class Elem,  
    class RXtraits = regex_traits<Elem>,  
    class basic_regex {  
public:  
    basic_regex();  
    explicit basic_regex(const Elem *ptr,  
        flag_type flags = ECMAScript);  
    basic_regex(const Elem *ptr, size_type len,  
        flag_type flags = ECMAScript);  
    basic_regex(const basic_regex& right);  
    template<class STtraits, class STalloc>  
        explicit basic_regex(const basic_string<Elem, STtraits, STalloc>& str,  
            flag_type flags = ECMAScript);  
    template<class InIt>  
        explicit basic_regex(InIt first, InIt last,  
            flag_type flags = ECMAScript);  
  
    basic_regex& operator=(const basic_regex& right);  
    basic_regex& operator=(const Elem *ptr);  
    template<class STtraits, class STalloc>  
        basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);  
    basic_regex& assign(const basic_regex& right);  
    basic_regex& assign(const Elem *ptr,  
        flag_type flags = ECMAScript);  
    basic_regex& assign(const Elem *ptr, size_type len,  
        flag_type flags = ECMAScript);  
    template<class STtraits, class STalloc>  
    basic_regex& assign(const basic_string<Elem, STtraits, STalloc>& str,  
        flag_type flags = ECMAScript);  
    template<class InIt>  
        basic_regex& assign(InIt first, InIt last,  
            flag_type flags = ECMAScript);  
  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
    void swap(basic_regex& other) throw();  
    unsigned mark_count() const;  
    flag_type flags() const;  
  
    typedef Elem value_type;  
    typedef regex_constants::syntax_option_type flag_type;  
    typedef typename RXtraits::locale_type locale_type;  
    static const flag_type icase = regex_constants::icase;  
    static const flag_type nosubs = regex_constants::nosubs;  
    static const flag_type optimize = regex_constants::optimize;  
    static const flag_type collate = regex_constants::collate;  
    static const flag_type ECMAScript = regex_constants::ECMAScript;  
    static const flag_type basic = regex_constants::basic;  
    static const flag_type extended = regex_constants::extended;  
    static const flag_type awk = regex_constants::awk;  
    static const flag_type grep = regex_constants::grep;  
    static const flag_type egrep = regex_constants::egrep;  
private:  
    RXtraits traits;    // exposition only  
    };  
```  
  
#### Paramètres  
 `Elem`  
 Type des éléments à faire correspondre.  
  
 `RXtraits`  
 Classe Traits des éléments.  
  
## Notes  
 La classe de modèle décrit un objet qui contient une expression régulière.  Les objets de cette classe de modèle peuvent être transmis aux fonctions de modèle [regex\_match, fonction](../Topic/regex_match%20Function.md), [regex\_search, fonction](../Topic/regex_search%20Function.md) et [regex\_replace, fonction](../Topic/regex_replace%20Function.md), avec les arguments de chaîne de texte appropriés, afin de rechercher le texte correspondant à l'expression régulière.  Il existe deux spécialisations de cette classe de modèle : les définitions de type [regex, typedef](../Topic/regex%20Typedef.md) pour les éléments de type `char`, et [wregex, typedef](../Topic/wregex%20Typedef.md) pour les éléments de type `wchar_t`.  
  
 L'argument de modèle `RXtraits` décrit plusieurs propriétés importantes de la syntaxe des expressions régulières prises en charge par la classe de modèle.  Une classe qui spécifie ces caractéristiques d'expression régulière doit avoir la même interface externe qu'un objet de la classe de modèle [Classe regex\_traits](../standard-library/regex-traits-class.md).  
  
 Certaines fonctions acceptent une séquence d'opérande qui définit une expression régulière.  Vous pouvez spécifier cette séquence d'opérande de plusieurs façons :  
  
 `ptr` \-\- une séquence se terminant par null \(telle qu'une chaîne en C, pour un `Elem` de type `char`\) commençant à `ptr` \(qui doit être un pointeur null\), où l'élément de fin est la valeur `value_type()` et ne fait pas partie de la séquence d'opérande.  
  
 `ptr`, `count` \-\- une séquence d'éléments `count` commençant à `ptr` \(qui ne doit pas être un pointeur null\).  
  
 `str` \-\- la séquence spécifiée par l'objet `basic_string` `str`.  
  
 `first`, `last` \-\- une séquence d'éléments délimités par les itérateurs `first` et `last`, dans la plage `[first, last)`.  
  
 `right` \-\- l'objet `basic_regex` `right`.  
  
 Ces fonctions membres acceptent également un argument `flags` qui spécifie plusieurs options pour l'interprétation de l'expression régulière, en plus de celles décrites par le type `RXtraits`.  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_match, fonction](../Topic/regex_match%20Function.md)   
 [regex\_search, fonction](../Topic/regex_search%20Function.md)   
 [regex\_replace, fonction](../Topic/regex_replace%20Function.md)   
 [regex, typedef](../Topic/regex%20Typedef.md)   
 [wregex, typedef](../Topic/wregex%20Typedef.md)   
 [Classe regex\_traits](../standard-library/regex-traits-class.md)