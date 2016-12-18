---
title: "Classe regex_traits | Microsoft Docs"
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
  - "regex_traits"
  - "std::tr1::regex_traits"
  - "std.tr1.regex_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits, classe [TR1]"
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Classe regex_traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit les caractéristiques des éléments pour la mise en correspondance.  
  
## Syntaxe  
  
```  
template<class Elem>  
    struct regex_traits {  
    regex_traits();  
  
    static size_type length(const char_type *str);  
    char_type translate(char_type ch) const;  
    char_type translate_nocase(char_type ch) const;  
    template<class FwdIt>  
        string_type transform(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type transform_primary(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        char_class_type lookup_classname(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type lookup_collatename(FwdIt first, FwdIt last) const;  
    bool isctype(char_type ch, char_class_type cls) const;  
    int value(Elem ch, int base) const;  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
  
    typedef Elem char_type;  
    typedef T6 size_type;  
    typedef basic_string<Elem> string_type;  
    typedef T7 locale_type;  
    typedef T8 char_class_type;  
    };  
```  
  
#### Paramètres  
 `Elem`  
 Type d’élément à décrire.  
  
## Notes  
 La classe de modèle décrit différents traits d’expressions régulières pour le type `Elem`. La classe de modèle [basic\_regex, classe](../standard-library/basic-regex-class.md) utilise ces informations pour manipuler les éléments de type `Elem`.  
  
 Chaque objet `regex_traits` a un objet de type `regex_traits::locale` qui est utilisé par certaines de ses fonctions membres. Les paramètres régionaux par défaut sont une copie de `regex_traits::locale()`. La fonction membre `imbue` remplace l’objet de paramètres régionaux , et la fonction membre `getloc` retourne une copie de l’objet de paramètres régionaux.  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits](../standard-library/regex-traits-class.md)   
 [regex\_traits \< char \> \(classe\)](../standard-library/regex-traits-char-class.md)   
 [regex\_traits\<wchar\_t\>, classe](../standard-library/regex-traits-wchar-t-class.md)