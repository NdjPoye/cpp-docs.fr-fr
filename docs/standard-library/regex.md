---
title: '&lt;regex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <regex>
dev_langs:
- C++
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 4e172f8bf72fd528027c333cf411a307aa97d786
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt"></a>&lt;regex&gt;
Définit une classe de modèle pour analyser des [expressions régulières (C++)](../standard-library/regular-expressions-cpp.md), ainsi que plusieurs fonctions et classes de modèle pour rechercher dans du texte des correspondances à un objet d’expression régulière.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <regex>  
```  
  
## <a name="remarks"></a>Notes  
 Pour créer un objet d’expression régulière, utilisez la classe de modèle [basic_regex](../standard-library/basic-regex-class.md) ou l’une de ses spécialisations, [regex](../standard-library/regex-typedefs.md#regex_typedef) et [wregex](../standard-library/regex-typedefs.md#wregex_typedef), avec les indicateurs de syntaxe de type [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#regex_constants__syntax_option_type).  
  
 Pour rechercher dans du texte des correspondances à un objet d’expression régulière, utilisez les fonctions de modèle [regex_match](../standard-library/regex-functions.md#regex_match_function) et [regex_search](../standard-library/regex-functions.md#regex_search_function) avec les indicateurs de correspondance de type [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type). Ces fonctions retournent des résultats à l’aide de la classe de modèle [match_results](../standard-library/match-results-class.md) et de ses spécialisations, [cmatch](../standard-library/regex-typedefs.md#cmatch_typedef), [wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef), [smatch](../standard-library/regex-typedefs.md#smatch_typedef) et [wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef), ainsi que la classe de modèle [sub_match](../standard-library/sub-match-class.md) et ses spécialisations, [csub_match](../standard-library/regex-typedefs.md#csub_match_typedef), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef), [ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef) et [wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef).  
  
 Pour remplacer du texte qui correspond à un objet d’expression régulière, utilisez la fonction de modèle [regex_replace](../standard-library/regex-functions.md#regex_replace_function) avec les indicateurs de correspondance de type [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type).  
  
 Pour itérer au sein de plusieurs correspondances d’un objet d’expression régulière, utilisez les classes de modèle [regex_iterator](../standard-library/regex-iterator-class.md) et [regex_token_iterator](../standard-library/regex-token-iterator-class.md) ou l’une de ses spécialisations, [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef) ou [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef), avec les indicateurs de correspondance de type [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type).  
  
 Pour modifier les détails de la grammaire des expressions régulières, écrivez une classe qui implémente les caractéristiques d'expression régulière.  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[basic_regex](../standard-library/basic-regex-class.md)|Encapsule une expression régulière.|  
|[match_results](../standard-library/match-results-class.md)|Contient une séquence de sous-correspondances.|  
|[regex_constants](../standard-library/regex-constants-class.md)|Contient des constantes assorties.|  
|[regex_error](../standard-library/regex-error-class.md)|Signale une expression régulière incorrecte.|  
|[regex_iterator](../standard-library/regex-iterator-class.md)|Itère au sein des résultats de mise en correspondance.|  
|[regex_traits](../standard-library/regex-traits-class.md)|Décrit les caractéristiques des éléments pour la mise en correspondance.|  
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Décrit les caractéristiques de `char` pour la mise en correspondance.|  
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Décrit les caractéristiques de `wchar_t` pour la mise en correspondance.|  
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Itère au sein des sous-correspondances.|  
|[sub_match](../standard-library/sub-match-class.md)|Décrit une sous-correspondance.|  
  
### <a name="type-definitions"></a>Définitions de types  
  
|||  
|-|-|  
|[cmatch](../standard-library/regex-typedefs.md#cmatch_typedef)|Définition de type pour `char``match_results`.|  
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef)|Définition de type pour `char``regex_iterator`.|  
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef)|Définition de type pour `char``regex_token_iterator`.|  
|[csub_match](../standard-library/regex-typedefs.md#csub_match_typedef)|Définition de type pour `char``sub_match`.|  
|[regex](../standard-library/regex-typedefs.md#regex_typedef)|Définition de type pour `char``basic_regex`.|  
|[smatch](../standard-library/regex-typedefs.md#smatch_typedef)|Définition de type pour `string``match_results`.|  
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef)|Définition de type pour `string``regex_iterator`.|  
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef)|Définition de type pour `string``regex_token_iterator`.|  
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef)|Définition de type pour `string``sub_match`.|  
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef)|Définition de type pour `wchar_t``match_results`.|  
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef)|Définition de type pour `wchar_t``regex_iterator`.|  
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef)|Définition de type pour `wchar_t``regex_token_iterator`.|  
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef)|Définition de type pour `wchar_t``sub_match`.|  
|[wregex](../standard-library/regex-typedefs.md#wregex_typedef)|Définition de type pour `wchar_t``basic_regex`.|  
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef)|Définition de type pour `wstring``match_results`.|  
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef)|Définition de type pour `wstring``regex_iterator`.|  
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef)|Définition de type pour `wstring``regex_token_iterator`.|  
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef)|Définition de type pour `wstring``sub_match`.|  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[regex_match](../standard-library/regex-functions.md#regex_match_function)|Correspond exactement à une expression régulière.|  
|[regex_replace](../standard-library/regex-functions.md#regex_replace_function)|Remplace des expressions régulières mises en correspondance.|  
|[regex_search](../standard-library/regex-functions.md#regex_search_function)|Recherche une correspondance d'expression régulière.|  
|[swap](../standard-library/regex-functions.md#swap_function)|Échange des objets `basic_regex` ou `match_results`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](../standard-library/regex-operators.md#operator_eq_eq)|Comparaison de différents objets, égal.|  
|[operator!=](../standard-library/regex-operators.md#operator_neq)|Comparaison de différents objets, n'est pas égal.|  
|[operator<](../standard-library/regex-operators.md#operator_lt_)|Comparaison de différents objets, inférieur à.|  
|[operator\<=](../standard-library/regex-operators.md#operator_lt__eq)|Comparaison de différents objets, inférieur ou égal à.|  
|[operator>](../standard-library/regex-operators.md#operator_gt_)|Comparaison de différents objets, supérieur à.|  
|[operator>=](../standard-library/regex-operators.md#operator_gt__eq)|Comparaison de différents objets, supérieur ou égal à.|  
|[operator<<](../standard-library/regex-operators.md#operator_lt__lt_)|Insère un `sub_match` dans un flux.|  
  
## <a name="see-also"></a>Voir aussi  
[Expressions régulières (C++)](../standard-library/regular-expressions-cpp.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[regex_error, classe](../standard-library/regex-error-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[\<regex>, opérateurs](../standard-library/regex-operators.md)  
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)  
[regex_traits, classe](../standard-library/regex-traits-class.md)  
[\<regex>, typedefs](../standard-library/regex-typedefs.md)  




