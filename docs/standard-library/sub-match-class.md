---
title: "sub_match, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sub_match"
  - "std::tr1::sub_match"
  - "std.tr1.sub_match"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sub_match (classe) (TR1)"
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sub_match, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit une sous\-correspondance.  
  
## Syntaxe  
  
```  
template<class BidIt>  
    class sub_match  
        : public std::pair<BidIt, BidIt> {  
public:  
    bool matched;  
    int compare(const sub_match& right) const;  
    int compare(const basic_string<value_type>& right) const;  
    int compare(const value_type *right) const;  
    difference_type length() const;  
    operator basic_string<value_type>() const;  
    basic_string<value_type> str() const;  
    typedef typename iterator_traits<BidIt>::value_type value_type;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef BidIt iterator;  
    };  
```  
  
#### Paramètres  
 `BidIt`  
 Type d'itérateur pour les sous\-correspondances.  
  
## Notes  
 La classe de modèle décrit un objet qui désigne une séquence de caractères correspondant à un groupe de capture dans un appel à [regex\_match, fonction](../Topic/regex_match%20Function.md) ou [regex\_search, fonction](../Topic/regex_search%20Function.md). Les objets de type [match\_results, classe](../standard-library/match-results-class.md) contiennent un tableau de ces objets, un pour chaque groupe de capture de l’expression régulière utilisée dans la recherche.  
  
 Si le groupe de capture n’a aucune correspondance, le membre de données `matched` de l’objet a la valeur false, et les deux itérateurs `first` et `second` \(hérités du `std::pair` de base\) sont égaux. Si le groupe de capture a une correspondance, `matched` a la valeur true et l’itérateur `first` pointe vers le premier caractère de la séquence cible correspondant au groupe de capture. En outre, l’itérateur `second` pointe vers la position située après le dernier caractère de la séquence cible correspondant au groupe de capture. Notez que pour une correspondance de longueur nulle, le membre `matched` a la valeur true. Par ailleurs, les deux itérateurs sont égaux et pointent vers la position de la correspondance.  
  
 Une correspondance de longueur nulle peut se produire quand un groupe de capture se compose uniquement d’une assertion, ou d’une répétition n’autorisant aucune répétition. Exemple :  
  
 « ^ » correspond à la séquence cible « a ». L’objet `sub_match` correspondant au groupe de capture 0 contient les itérateurs qui pointent vers le premier caractère de la séquence.  
  
 « b\(a\*\)b » correspond à la séquence cible « bb ». L’objet `sub_match` correspondant au groupe de capture 1 contient les itérateurs qui pointent vers le second caractère de la séquence.  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)   
 [sub\_match](../standard-library/sub-match-class.md)   
 [regex\_match, fonction](../Topic/regex_match%20Function.md)   
 [regex\_search, fonction](../Topic/regex_search%20Function.md)