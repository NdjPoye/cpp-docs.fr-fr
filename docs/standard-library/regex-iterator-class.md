---
title: regex_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_iterator
- std::regex_iterator
- regex/std::regex_iterator
- std::regex_iterator::operator==
- regex/std::regex_iterator::operator==
- std::regex_iterator::operator!=
- regex/std::regex_iterator::operator!=
- std::regex_iterator::operator*
- regex/std::regex_iterator::operator*
- std::regex_iterator::operator->
- regex/std::regex_iterator::operator->
- std::regex_iterator::operator++
- regex/std::regex_iterator::operator++
dev_langs:
- C++
helpviewer_keywords:
- regex_iterator class
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 8bfed3b74020bce20f18700d30573f01cdfd2adc
ms.lasthandoff: 02/24/2017

---
# <a name="regexiterator-class"></a>regex_iterator, classe
Classe d’itérateur pour les correspondances.  
  
## <a name="syntax"></a>Syntaxe  
```
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator {  
public:  
   typedef basic_regex<Elem, RXtraits> regex_type;  
   typedef match_results<BidIt> value_type;  
   typedef std::forward_iterator_tag iterator_category;  
   typedef std::ptrdiff_t difference_type;  
   typedef const match_results<BidIt>* pointer;  
   typedef const match_results<BidIt>& reference;  

   regex_iterator();
   regex_iterator(
      BidIt first, BidIt last, const regex_type& re,  
      regex_constants::match_flag_type f = regex_constants::match_default);

   bool operator==(const regex_iterator& right);
   bool operator!=(const regex_iterator& right);
   const match_results<BidIt>& operator*();
   const match_results<BidIt> * operator->();
   regex_iterator& operator++();
   regex_iterator& operator++(int);

private:
   BidIt begin; // exposition only  
   BidIt end; // exposition only  
   regex_type *pregex;     // exposition only  
   regex_constants::match_flag_type flags; // exposition only  
   match_results<BidIt> match; // exposition only  
   };  
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur pour les sous-correspondances.  
  
 `Elem`  
 Type des éléments à faire correspondre.  
  
 `RXtraits`  
 Classe Traits des éléments.  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle décrit un objet itérateur forward constant. Elle extrait les objets de type `match_results<BidIt>` en appliquant à plusieurs reprises son objet d’expression régulière `*pregex` à la séquence de caractères définie par la plage d’itérateurs `[begin, end)`.  
  
## <a name="examples"></a>Exemples  
 Consultez les rubriques suivantes pour obtenir des exemples d’expressions régulières :  
  
- [regex_match, fonction](../standard-library/regex-functions.md#regex_match_function)  
  
- [regex_replace, fonction](../standard-library/regex-functions.md#regex_replace_function)  
  
- [regex_search, fonction](../standard-library/regex-functions.md#regex_search_function)  
  
- [swap, fonction](../standard-library/regex-functions.md#swap_function)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<regex>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameregexiteratordifferencetypea--regexiteratordifferencetype"></a><a name="regex_iterator__difference_type"></a>  regex_iterator::difference_type  
 Type d’une différence d’itérateur.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `std::ptrdiff_t`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_difference_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoriteratorcategorya--regexiteratoriteratorcategory"></a><a name="regex_iterator__iterator_category"></a>  regex_iterator::iterator_category  
 Type de la catégorie d'itérateur.  
  
```  
typedef std::forward_iterator_tag iterator_category;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `std::forward_iterator_tag`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_iterator_category.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatorneqa--regexiteratoroperator"></a><a name="regex_iterator__operator_neq"></a>  regex_iterator::operator!=  
 Compare l’inégalité d’itérateurs.  
  
```  
bool operator!=(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Itérateur auquel comparer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `!(*this == right)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatorstara--regexiteratoroperator"></a><a name="regex_iterator__operator_star"></a>  regex_iterator::operator*  
 Accède à la correspondance désignée.  
  
```  
const match_results<BidIt>& operator*();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la valeur stockée `match`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_operator_star.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatoraddadda--regexiteratoroperator"></a><a name="regex_iterator__operator_add_add"></a>  regex_iterator::operator++  
 Incrémente l'itérateur.  
  
```  
regex_iterator& operator++();
regex_iterator& operator++(int);
```  
  
### <a name="remarks"></a>Notes  
 Si la correspondance actuelle ne comporte aucun caractère, le premier opérateur appelle `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`. Sinon, il avance la valeur stockée `begin` pour pointer vers le premier caractère situé après la correspondance actuelle, puis appelle `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. Dans chaque cas, si la recherche n’aboutit pas, l’opérateur assigne à l’objet un itérateur de fin de séquence. L’opérateur retourne l’objet.  
  
 Le deuxième opérateur effectue une copie de l'objet, incrémente l'objet, puis retourne la copie.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_operator_inc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatoreqa--regexiteratoroperator"></a><a name="regex_iterator__operator_eq"></a>  regex_iterator::operator=  
 Compare des itérateurs pour déterminer s’ils sont égaux.  
  
```  
bool operator==(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Itérateur auquel comparer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la valeur true si `*this` et `right` sont des itérateurs de séquence de fin, ou si aucun d’eux n’est un itérateur de fin de séquence et `begin == right.begin`, `end == right.end`, `pregex == right.pregex`et `flags == right.flags`. Sinon, elle retourne false.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_operator_as.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperator-gta--regexiteratoroperator-gt"></a><a name="regex_iterator__operator-_gt_"></a>  regex_iterator::operator-&gt;  
 Accède à la correspondance désignée.  
  
```  
const match_results<BidIt> * operator->();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’adresse de la valeur stockée `match`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_operator_arrow.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorpointera--regexiteratorpointer"></a><a name="regex_iterator__pointer"></a>  regex_iterator::pointer  
 Type d'un pointeur vers une correspondance.  
  
```  
typedef match_results<BidIt> *pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `match_results<BidIt>*`, où `BidIt` est le paramètre de modèle.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_pointer.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorreferencea--regexiteratorreference"></a><a name="regex_iterator__reference"></a>  regex_iterator::reference  
 Type d’une référence à une correspondance.  
  
```  
typedef match_results<BidIt>& reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `match_results<BidIt>&`, où `BidIt` est le paramètre de modèle.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorregexiteratora--regexiteratorregexiterator"></a><a name="regex_iterator__regex_iterator"></a>  regex_iterator::regex_iterator  
 Construit l’itérateur.  
  
```  
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,  
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la séquence à mettre en correspondance.  
  
 `last`  
 Fin de la séquence à mettre en correspondance.  
  
 `re`  
 Expression régulière pour les correspondances.  
  
 `f`  
 Indicateurs pour les correspondances.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur construit un itérateur de fin de séquence. Le deuxième constructeur initialise la valeur stockée `begin` avec `first`, la valeur stockée `end` avec `last`, la valeur stockée `pregex` avec `&re`, et la valeur stockée `flags` avec `f`. Il appelle ensuite `regex_search(begin, end, match, *pregex, flags)`. En cas d’échec de la recherche, le constructeur assigne à l’objet un itérateur de fin de séquence.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorregextypea--regexiteratorregextype"></a><a name="regex_iterator__regex_type"></a>  regex_iterator::regex_type  
 Type de l’expression régulière à mettre en correspondance.  
  
```  
typedef basic_regex<Elem, RXtraits> regex_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme de `basic_regex<Elem, RXtraits>`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_regex_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorvaluetypea--regexiteratorvaluetype"></a><a name="regex_iterator__value_type"></a>  regex_iterator::value_type  
 Type d'une correspondance.  
  
```  
typedef match_results<BidIt> value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `match_results<BidIt>`, où `BidIt` est le paramètre de modèle.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_iterator_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
## <a name="see-also"></a>Voir aussi  
[\<regex>](../standard-library/regex.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[regex_error, classe](../standard-library/regex-error-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[\<regex>, opérateurs](../standard-library/regex-operators.md)  
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)  
[regex_traits, classe](../standard-library/regex-traits-class.md)  
[\<regex>, typedefs](../standard-library/regex-typedefs.md)  

  

