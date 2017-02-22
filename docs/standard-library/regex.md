---
title: "&lt;regex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<regex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex (en-tête) (TR1)"
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;regex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit une classe de modèle pour analyser des [Expressions régulières \(C\+\+\)](../standard-library/regular-expressions-cpp.md) et plusieurs fonctions et classes de modèle pour rechercher dans du texte des correspondances à un objet d'expression régulière.  
  
## Syntaxe  
  
```  
#include <regex>  
```  
  
## Notes  
 Pour créer un objet d'expression régulière, utilisez la classe de modèle [basic\_regex, classe](../standard-library/basic-regex-class.md) ou l'une de ses spécialisations, [regex, typedef](../Topic/regex%20Typedef.md) et [wregex, typedef](../Topic/wregex%20Typedef.md), avec les indicateurs de syntaxe de type [regex\_constants::syntax\_option\_type](../Topic/regex_constants::syntax_option_type.md).  
  
 Pour rechercher dans du texte des correspondances à un objet d'expression régulière, utilisez les fonctions de modèle [regex\_match, fonction](../Topic/regex_match%20Function.md) et [regex\_search, fonction](../Topic/regex_search%20Function.md) avec les indicateurs de correspondance de type [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  Ces fonctions retournent des résultats à l'aide de la classe de modèle [match\_results, classe](../standard-library/match-results-class.md) et ses spécialisations, [cmatch, typedef](../Topic/cmatch%20Typedef.md), [wcmatch, typedef](../Topic/wcmatch%20Typedef.md), [smatch, typedef](../Topic/smatch%20Typedef.md) et [wsmatch, typedef](../Topic/wsmatch%20Typedef.md), ainsi que la classe de modèle [sub\_match, classe](../standard-library/sub-match-class.md) et ses spécialisations, [csub\_match, typedef](../Topic/csub_match%20Typedef.md), [wcsub\_match, typedef](../Topic/wcsub_match%20Typedef.md), [ssub\_match, typedef](../Topic/ssub_match%20Typedef.md) et [wssub\_match, typedef](../Topic/wssub_match%20Typedef.md).  
  
 Pour remplacer du texte qui correspond à un objet d'expression régulière, utilisez la fonction de modèle [regex\_replace, fonction](../Topic/regex_replace%20Function.md) avec les indicateurs de correspondance de type [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  
  
 Pour itérer au sein de plusieurs correspondances d'un objet d'expression régulière, utilisez les classes de modèle [regex\_iterator, classe](../standard-library/regex-iterator-class.md) et [regex\_token\_iterator, classe](../standard-library/regex-token-iterator-class.md) ou l'une de leurs spécialisations, [cregex\_iterator, typedef](../Topic/cregex_iterator%20Typedef.md), [sregex\_iterator, typedef](../Topic/sregex_iterator%20Typedef.md), [wcregex\_iterator, typedef](../Topic/wcregex_iterator%20Typedef.md), [wsregex\_iterator, typedef](../Topic/wsregex_iterator%20Typedef.md), [cregex\_token\_iterator, typedef](../Topic/cregex_token_iterator%20Typedef.md), [sregex\_token\_iterator, typedef](../Topic/sregex_token_iterator%20Typedef.md), [wcregex\_token\_iterator, typedef](../Topic/wcregex_token_iterator%20Typedef.md) ou [wsregex\_token\_iterator, typedef](../Topic/wsregex_token_iterator%20Typedef.md), avec les indicateurs de correspondance de type [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  
  
 Pour modifier les détails de la grammaire des expressions régulières, écrivez une classe qui implémente les caractéristiques d'expression régulière.  
  
### Classes  
  
|||  
|-|-|  
|[basic\_regex](../standard-library/basic-regex-class.md)|Encapsule une expression régulière.|  
|[match\_results](../standard-library/match-results-class.md)|Contient une séquence de sous\-correspondances.|  
|[regex\_constants](../standard-library/regex-constants-class.md)|Contient des constantes assorties.|  
|[regex\_error](../standard-library/regex-error-class.md)|Signale une expression régulière incorrecte.|  
|[regex\_iterator](../standard-library/regex-iterator-class.md)|Itère au sein des résultats de mise en correspondance.|  
|[regex\_traits](../standard-library/regex-traits-class.md)|Décrit les caractéristiques des éléments pour la mise en correspondance.|  
|[regex\_traits\<char\>](../standard-library/regex-traits-char-class.md)|Décrit les caractéristiques de `char` pour la mise en correspondance.|  
|[regex\_traits\<wchar\_t\>](../standard-library/regex-traits-wchar-t-class.md)|Décrit les caractéristiques de `wchar_t` pour la mise en correspondance.|  
|[regex\_token\_iterator](../standard-library/regex-token-iterator-class.md)|Itère au sein des sous\-correspondances.|  
|[sub\_match](../standard-library/sub-match-class.md)|Décrit une sous\-correspondance.|  
  
### Définitions de types  
  
|||  
|-|-|  
|[cmatch](../Topic/cmatch%20Typedef.md)|Définition de type pour `char` `match_results`.|  
|[cregex\_iterator](../Topic/cregex_iterator%20Typedef.md)|Définition de type pour `char` `regex_iterator`.|  
|[cregex\_token\_iterator](../Topic/cregex_token_iterator%20Typedef.md)|Définition de type pour `char` `regex_token_iterator`.|  
|[csub\_match](../Topic/csub_match%20Typedef.md)|Définition de type pour `char` `sub_match`.|  
|[regex](../Topic/regex%20Typedef.md)|Définition de type pour `char` `basic_regex`.|  
|[smatch](../Topic/smatch%20Typedef.md)|Définition de type pour `string` `match_results`.|  
|[sregex\_iterator](../Topic/sregex_iterator%20Typedef.md)|Définition de type pour `string` `regex_iterator`.|  
|[sregex\_token\_iterator](../Topic/sregex_token_iterator%20Typedef.md)|Définition de type pour `string` `regex_token_iterator`.|  
|[ssub\_match](../Topic/ssub_match%20Typedef.md)|Définition de type pour `string` `sub_match`.|  
|[wcmatch](../Topic/wcmatch%20Typedef.md)|Définition de type pour `wchar_t` `match_results`.|  
|[wcregex\_iterator](../Topic/wcregex_iterator%20Typedef.md)|Définition de type pour `wchar_t` `regex_iterator`.|  
|[wcregex\_token\_iterator](../Topic/wcregex_token_iterator%20Typedef.md)|Définition de type pour `wchar_t` `regex_token_iterator`.|  
|[wcsub\_match](../Topic/wcsub_match%20Typedef.md)|Définition de type pour `wchar_t` `sub_match`.|  
|[wregex](../Topic/wregex%20Typedef.md)|Définition de type pour `wchar_t` `basic_regex`.|  
|[wsmatch](../Topic/wsmatch%20Typedef.md)|Définition de type pour `wstring` `match_results`.|  
|[wsregex\_iterator](../Topic/wsregex_iterator%20Typedef.md)|Définition de type pour `wstring` `regex_iterator`.|  
|[wsregex\_token\_iterator](../Topic/wsregex_token_iterator%20Typedef.md)|Définition de type pour `wstring` `regex_token_iterator`.|  
|[wssub\_match](../Topic/wssub_match%20Typedef.md)|Définition de type pour `wstring` `sub_match`.|  
  
### Fonctions  
  
|||  
|-|-|  
|[regex\_match](../Topic/regex_match%20Function.md)|Correspond exactement à une expression régulière.|  
|[regex\_replace](../Topic/regex_replace%20Function.md)|Remplace des expressions régulières mises en correspondance.|  
|[regex\_search](../Topic/regex_search%20Function.md)|Recherche une correspondance d'expression régulière.|  
|[échange](../Topic/swap%20Function%20%3Cregex%3E.md)|Échange des objets `basic_regex` ou `match_results`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20%3Cregex%3E.md)|Comparaison de différents objets, égal.|  
|[operator\!\=](../Topic/operator!=%20%3Cregex%3E.md)|Comparaison de différents objets, n'est pas égal.|  
|[operator\<](../Topic/operator%3C%20%3Cregex%3E.md)|Comparaison de différents objets, inférieur à.|  
|[operator\<\=](../Topic/operator%3C=%20%3Cregex%3E.md)|Comparaison de différents objets, inférieur ou égal à.|  
|[operator\>](../Topic/operator%3E%20%3Cregex%3E.md)|Comparaison de différents objets, supérieur à.|  
|[operator\>\=](../Topic/operator%3E=%20%3Cregex%3E.md)|Comparaison de différents objets, supérieur ou égal à.|  
|[operator\<\<](../Topic/operator%3C%3C%20%3Cregex%3E.md)|Insère un `sub_match` dans un flux.|  
  
## Voir aussi  
 [Expressions régulières \(C\+\+\)](../standard-library/regular-expressions-cpp.md)