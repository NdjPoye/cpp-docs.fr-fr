---
title: '&lt;regex&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmatch
- std::cmatch
- regex/std::cmatch
- cregex_iterator
- std::cregex_iterator
- regex/std::cregex_iterator
- cregex_token_iterator
- std::cregex_token_iterator
- regex/std::cregex_token_iterator
- csub_match
- std::csub_match
- regex/std::csub_match
- regex
- std::regex
- regex/std::regex
- smatch
- std::smatch
- regex/std::smatch
- sregex_iterator
- std::sregex_iterator
- regex/std::sregex_iterator
- sregex_token_iterator
- std::sregex_token_iterator
- regex/std::sregex_token_iterator
- ssub_match
- std::ssub_match
- regex/std::ssub_match
- wcmatch
- std::wcmatch
- regex/std::wcmatch
- wcregex_iterator
- std::wcregex_iterator
- regex/std::wcregex_iterator
- wcregex_token_iterator
- std::wcregex_token_iterator
- regex/std::wcregex_token_iterator
- wcsub_match
- std::wcsub_match
- regex/std::wcsub_match
- wregex
- std::wregex
- regex/std::wregex
- wsmatch
- std::wsmatch
- regex/std::wsmatch
- wsregex_iterator
- std::wsregex_iterator
- regex/std::wsregex_iterator
- wsregex_token_iterator
- std::wsregex_token_iterator
- regex/std::wsregex_token_iterator
- wssub_match
- std::wssub_match
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 60822dd232399b27ccda3db829b636d817091a2d
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt;, typedefs
||||  
|-|-|-|  
|[cmatch, typedef](#cmatch_typedef)|[cregex_iterator, typedef](#cregex_iterator_typedef)|[cregex_token_iterator, typedef](#cregex_token_iterator_typedef)|  
|[csub_match, typedef](#csub_match_typedef)|[regex, typedef](#regex_typedef)|[smatch, typedef](#smatch_typedef)|  
|[sregex_iterator, typedef](#sregex_iterator_typedef)|[sregex_token_iterator, typedef](#sregex_token_iterator_typedef)|[ssub_match, typedef](#ssub_match_typedef)|  
|[wcmatch, typedef](#wcmatch_typedef)|[wcregex_iterator, typedef](#wcregex_iterator_typedef)|[wcregex_token_iterator, typedef](#wcregex_token_iterator_typedef)|  
|[wcsub_match, typedef](#wcsub_match_typedef)|[wregex, typedef](#wregex_typedef)|[wsmatch, typedef](#wsmatch_typedef)|  
|[wsregex_iterator, typedef](#wsregex_iterator_typedef)|[wsregex_token_iterator, typedef](#wsregex_token_iterator_typedef)|[wssub_match, typedef](#wssub_match_typedef)|  
  
##  <a name="a-namecmatchtypedefa--cmatch-typedef"></a><a name="cmatch_typedef"></a>  cmatch, typedef  
 Définition de type pour char match_results.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [match_results](../standard-library/match-results-class.md) pour les itérateurs de type `const char*`.  
  
##  <a name="a-namecregexiteratortypedefa--cregexiterator-typedef"></a><a name="cregex_iterator_typedef"></a>  cregex_iterator, typedef  
 Définition de type pour char regex_iterator.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_iterator](../standard-library/regex-iterator-class.md) pour les itérateurs de type `const char*`.  
  
##  <a name="a-namecregextokeniteratortypedefa--cregextokeniterator-typedef"></a><a name="cregex_token_iterator_typedef"></a>  cregex_token_iterator, typedef  
 Définition de type pour char regex_token_iterator  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_token_iterator](../standard-library/regex-token-iterator-class.md) pour les itérateurs de type `const char*`.  
  
##  <a name="a-namecsubmatchtypedefa--csubmatch-typedef"></a><a name="csub_match_typedef"></a>  csub_match, typedef  
 Définition de type pour char sub_match.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [sub_match](../standard-library/sub-match-class.md) pour les itérateurs de type `const char*`.  
  
##  <a name="a-nameregextypedefa--regex-typedef"></a><a name="regex_typedef"></a>  regex, typedef  
 Définition de type pour char basic_regex.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [basic_regex](../standard-library/basic-regex-class.md) pour les itérateurs de type `char`.  
  
> [!NOTE]
>  L’utilisation de caractères étendus a des résultats imprévisibles avec `regex`. Les valeurs en dehors de la plage 0 à 127 peuvent entraîner un comportement non défini.  
  
##  <a name="a-namesmatchtypedefa--smatch-typedef"></a><a name="smatch_typedef"></a>  smatch, typedef  
 Définition de type pour string match_results.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [match_results](../standard-library/match-results-class.md) pour les itérateurs de type `string::const_iterator`.  
  
##  <a name="a-namesregexiteratortypedefa--sregexiterator-typedef"></a><a name="sregex_iterator_typedef"></a>  sregex_iterator, typedef  
 Définition du type pour string regex_iterator.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_iterator](../standard-library/regex-iterator-class.md) pour les itérateurs de type `string::const_iterator`.  
  
##  <a name="a-namesregextokeniteratortypedefa--sregextokeniterator-typedef"></a><a name="sregex_token_iterator_typedef"></a>  sregex_token_iterator, typedef  
 Définition de type pour string regex_token_iterator.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_token_iterator](../standard-library/regex-token-iterator-class.md) pour les itérateurs de type `string::const_iterator`.  
  
##  <a name="a-namessubmatchtypedefa--ssubmatch-typedef"></a><a name="ssub_match_typedef"></a> ssub_match, typedef  
 Définition de type pour string sub_match.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [sub_match](../standard-library/sub-match-class.md) pour les itérateurs de type `string::const_iterator`.  
  
##  <a name="a-namewcmatchtypedefa--wcmatch-typedef"></a><a name="wcmatch_typedef"></a>  wcmatch, typedef  
 Définition de type pour wchar_t match_results.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [match_results](../standard-library/match-results-class.md) pour les itérateurs de type `const wchar_t*`.  
  
##  <a name="a-namewcregexiteratortypedefa--wcregexiterator-typedef"></a><a name="wcregex_iterator_typedef"></a>  wcregex_iterator, typedef  
 Définition de type pour wchar_t regex_iterator.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_iterator](../standard-library/regex-iterator-class.md) pour les itérateurs de type `const wchar_t*`.  
  
##  <a name="a-namewcregextokeniteratortypedefa--wcregextokeniterator-typedef"></a><a name="wcregex_token_iterator_typedef"></a>  wcregex_token_iterator, typedef  
 Définition de type pour wchar_t regex_token_iterator.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_token_iterator](../standard-library/regex-token-iterator-class.md) pour les itérateurs de type `const wchar_t*`.  
  
##  <a name="a-namewcsubmatchtypedefa--wcsubmatch-typedef"></a><a name="wcsub_match_typedef"></a>  wcsub_match, typedef  
 Définition de type pour wchar_t sub_match.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [sub_match](../standard-library/sub-match-class.md) pour les itérateurs de type `const wchar_t*`.  
  
##  <a name="a-namewregextypedefa--wregex-typedef"></a><a name="wregex_typedef"></a>  wregex, typedef  
 Définition de type pour wchar_t basic_regex.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [basic_regex](../standard-library/basic-regex-class.md) pour les itérateurs de type `wchar_t`.  
  
##  <a name="a-namewsmatchtypedefa--wsmatch-typedef"></a><a name="wsmatch_typedef"></a>  wsmatch, typedef  
 Définition de type pour wstring match_results.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [match_results](../standard-library/match-results-class.md) pour les itérateurs de type `wstring::const_iterator`.  
  
##  <a name="a-namewsregexiteratortypedefa--wsregexiterator-typedef"></a><a name="wsregex_iterator_typedef"></a>  wsregex_iterator, typedef  
 Définition de type pour wstring regex_iterator.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_iterator](../standard-library/regex-iterator-class.md) pour les itérateurs de type `wstring::const_iterator`.  
  
##  <a name="a-namewsregextokeniteratortypedefa--wsregextokeniterator-typedef"></a><a name="wsregex_token_iterator_typedef"></a>  wsregex_token_iterator, typedef  
 Définition de type pour wstring regex_token_iterator.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [regex_token_iterator](../standard-library/regex-token-iterator-class.md) pour les itérateurs de type `wstring::const_iterator`.  
  
##  <a name="a-namewssubmatchtypedefa--wssubmatch-typedef"></a><a name="wssub_match_typedef"></a>  wssub_match, typedef  
 Définition de type pour wstring sub_match.  
  
```  
typedef sub_match<wstring::const_iterator> wssub_match;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une spécialisation de la classe de modèle [sub_match](../standard-library/sub-match-class.md) pour les itérateurs de type `wstring::const_iterator`.  
  
## <a name="see-also"></a>Voir aussi  
[\<regex>](../standard-library/regex.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[regex_error, classe](../standard-library/regex-error-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[\<regex>, opérateurs](../standard-library/regex-operators.md)  
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)  
[regex_traits, classe](../standard-library/regex-traits-class.md)  

