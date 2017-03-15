---
title: regex_token_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_token_iterator
- std::regex_token_iterator
- regex/std::regex_token_iterator
- std::regex_token_iterator::regex_type
- regex/std::regex_token_iterator::regex_type
- std::regex_token_iterator::value_type
- regex/std::regex_token_iterator::value_type
- std::regex_token_iterator::iterator_category
- regex/std::regex_token_iterator::iterator_category
- std::regex_token_iterator::difference_type
- regex/std::regex_token_iterator::difference_type
- std::regex_token_iterator::pointer
- regex/std::regex_token_iterator::pointer
- std::regex_token_iterator::reference
- regex/std::regex_token_iterator::reference
- std::regex_token_iterator::operator==
- regex/std::regex_token_iterator::operator==
- std::regex_token_iterator::operator!=
- regex/std::regex_token_iterator::operator!=
- std::regex_token_iterator::operator*
- regex/std::regex_token_iterator::operator*
- std::regex_token_iterator::operator->
- regex/std::regex_token_iterator::operator->
- std::regex_token_iterator::operator++
- regex/std::regex_token_iterator::operator++
- std::regex_token_iterator::operator!=
- regex/std::regex_token_iterator::operator!=
dev_langs:
- C++
helpviewer_keywords:
- regex_token_iterator class
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
caps.latest.revision: 15
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 55da414f0a743fab278cb47441efe04e82ac3279
ms.lasthandoff: 02/24/2017

---
# <a name="regextokeniterator-class"></a>regex_token_iterator, classe
Classe d’itérateur pour les sous-correspondances.  
  
## <a name="syntax"></a>Syntaxe  
```  
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator {  
public:  
   typedef basic_regex<Elem, RXtraits> regex_type;  
   typedef sub_match<BidIt> value_type;  
   typedef std::forward_iterator_tag iterator_category;  
   typedef std::ptrdiff_t difference_type;  
   typedef const sub_match<BidIt> *pointer;  
   typedef const sub_match<BidIt>& reference;  
   regex_token_iterator();
   regex_token_iterator(
      BidIt first, BidIt last,  
      const regex_type& re, int submatch = 0,  
      regex_constants::match_flag_type f = regex_constants::match_default);
   regex_token_iterator(
      BidIt first, BidIt last,  
      const regex_type& re, const std::vector<int> submatches,  
      regex_constants::match_flag_type f = regex_constants::match_default);
   template <std::size_t N>  
   regex_token_iterator(
      BidIt first, BidIt last,  
      const regex_type& re, const int (&submatches)[N],  
      regex_constants::match_flag_type f = regex_constants::match_default);
   bool operator==(const regex_token_iterator& right);
   bool operator!=(const regex_token_iterator& right);
   const basic_string<Elem>& operator*();
   const basic_string<Elem> * operator->();
   regex_token_iterator& operator++();
   regex_token_iterator& operator++(int);
private:  
   regex_iterator<BidIt, Elem, RXtraits> it; // exposition only  
   vector<int> subs;   // exposition only  
   int pos;  // exposition only  
   };  
```  
#### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur pour les sous-correspondances.  
  
 `Elem`  
 Type des éléments à faire correspondre.  
  
 `RXtraits`  
 Classe Traits des éléments.  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle décrit un objet itérateur forward constant. D’un point de vue conceptuel, elle contient un objet `regex_iterator` utilisé pour la recherche d’expressions régulières dans une séquence de caractères. Elle extrait des objets de type `sub_match<BidIt>` représentant les sous-correspondances identifiées par les valeurs d’index dans le vecteur stocké `subs` pour chaque correspondance d’expression régulière.  
  
 La valeur d’index -1 désigne la séquence de caractères qui commence immédiatement après la fin de la correspondance d’expression régulière précédente, ou le début de la séquence de caractères en l’absence de correspondance d’expression régulière précédente. Par ailleurs, la séquence s’étend jusqu’au premier caractère (sans l’inclure) de la correspondance d’expression régulière actuelle, ou jusqu’à la fin de la séquence de caractères en l’absence de correspondance actuelle. Toute autre valeur d’index `idx` désigne le contenu du groupe de capture situé dans `it.match[idx]`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<regex>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameregextokeniteratordifferencetypea--regextokeniteratordifferencetype"></a><a name="regex_token_iterator__difference_type"></a>  regex_token_iterator::difference_type  
 Type d’une différence d’itérateur.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `std::ptrdiff_t`.  
  
### <a name="example"></a>Exemple  
  
```cpp    
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
```  
  
##  <a name="a-nameregextokeniteratoriteratorcategorya--regextokeniteratoriteratorcategory"></a><a name="regex_token_iterator__iterator_category"></a>  regex_token_iterator::iterator_category  
 Type de la catégorie d'itérateur.  
  
```  
typedef std::forward_iterator_tag iterator_category;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `std::forward_iterator_tag`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_iterator_category.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratoroperatorneqa--regextokeniteratoroperator"></a><a name="regex_token_iterator__operator_neq"></a>  regex_token_iterator::operator!=  
 Compare l’inégalité d’itérateurs.  
  
```  
bool operator!=(const regex_token_iterator& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Itérateur auquel comparer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `!(*this == right)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratoroperatorstara--regextokeniteratoroperator"></a><a name="regex_token_iterator__operator_star"></a>  regex_token_iterator::operator*  
 Accède à la sous-correspondance désignée.  
  
```  
const sub_match<BidIt>& operator*();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne un objet `sub_match<BidIt>` représentant le groupe de capture identifié par la valeur d’index `subs[pos]`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_operator_star.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratoroperatoraddadda--regextokeniteratoroperator"></a><a name="regex_token_iterator__operator_add_add"></a>  regex_token_iterator::operator++  
 Incrémente l'itérateur.  
  
```  
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```  
  
### <a name="remarks"></a>Notes  
 Si l'itérateur stocké `it` est un itérateur de fin de séquence, le premier opérateur définit la valeur stockée `pos` à la valeur de `subs.size()` (ce qui crée un itérateur de fin de séquence). Sinon, l'opérateur incrémente la valeur stockée `pos` ; si le résultat est égal à la valeur `subs.size()`, il définit la valeur stockée `pos` à zéro et incrémente l'itérateur stocké `it`. Si, suite à son incrémentation, l'itérateur est inégal à un itérateur de fin de séquence, l'opérateur ne fait rien de plus. Sinon, si la fin de la correspondance précédente était à la fin de la séquence de caractères, l'opérateur définit la valeur stockée de `pos` à `subs.size()`. Sinon, l'opérateur incrémente de manière répétée la valeur stockée `pos` jusqu'à `pos == subs.size()` ou `subs[pos] == -1` (garantissant ainsi que le déréférencement suivant de l'itérateur retournera la fin de la séquence de caractères si l'une des valeurs d'index est -1). Dans tous les cas, l'opérateur retourne l'objet.  
  
 Le deuxième opérateur effectue une copie de l'objet, incrémente l'objet, puis retourne la copie.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_operator_inc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratoroperatoreqeqa--regextokeniteratoroperator"></a><a name="regex_token_iterator__operator_eq_eq"></a>  regex_token_iterator::operator==  
 Compare des itérateurs pour déterminer s’ils sont égaux.  
  
```  
bool operator==(const regex_token_iterator& right);
```  
  
### <a name="parameters"></a>Paramètres  
 droite  
 Itérateur auquel comparer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `it == right.it && subs == right.subs && pos == right.pos`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_operator_eq.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratoroperator-gta--regextokeniteratoroperator-gt"></a><a name="regex_token_iterator__operator-_gt_"></a>  regex_token_iterator::operator-&gt;  
 Accède à la sous-correspondance désignée.  
  
```  
const sub_match<BidIt> * operator->();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne un pointeur vers un objet `sub_match<BidIt>` représentant le groupe de capture identifié par la valeur d’index `subs[pos]`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_operator_arrow.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratorpointera--regextokeniteratorpointer"></a><a name="regex_token_iterator__pointer"></a>  regex_token_iterator::pointer  
 Type d'un pointeur vers une correspondance.  
  
```  
typedef sub_match<BidIt> *pointer;  
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_pointer.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `sub_match<BidIt>*`, où `BidIt` est le paramètre de modèle.  
  
##  <a name="a-nameregextokeniteratorreferencea--regextokeniteratorreference"></a><a name="regex_token_iterator__reference"></a>  regex_token_iterator::reference  
 Type d’une référence à une sous-correspondance.  
  
```  
typedef sub_match<BidIt>& reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `sub_match<BidIt>&`, où `BidIt` est le paramètre de modèle.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratorregextokeniteratora--regextokeniteratorregextokeniterator"></a><a name="regex_token_iterator__regex_token_iterator"></a>  regex_token_iterator::regex_token_iterator  
 Construit l’itérateur.  
  
```  
regex_token_iterator();

regex_token_iterator(BidIt first, BidIt last,  
    const regex_type& re, int submatch = 0,  
    regex_constants::match_flag_type f = regex_constants::match_default);

regex_token_iterator(BidIt first, BidIt last,  
    const regex_type& re, const vector<int> submatches,  
    regex_constants::match_flag_type f = regex_constants::match_default);

template <std::size_t N>  
regex_token_iterator(BidIt first, BidIt last,  
    const regex_type& re, const int (&submatches)[N],  
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
 Le premier constructeur construit un itérateur de fin de séquence.  
  
 Le second constructeur construit un objet dont l’itérateur stocké `it` est initialisé à `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, dont le vecteur stocké `subs` contient seulement un entier, ayant la valeur `submatch`, et dont la valeur stockée `pos` est égale à zéro. Remarque : l’objet résultant extrait la sous-correspondance identifiée par la valeur d’index `submatch` pour chaque correspondance d’expression régulière réussie.  
  
 Le troisième constructeur construit un objet dont l’itérateur stocké `it` est initialisé à `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, dont le vecteur stocké `subs` contient une copie de l’argument de constructeur `submatches`, et dont la valeur stockée `pos` est égale à zéro.  
  
 Le quatrième constructeur construit un objet dont l’itérateur stocké `it` est initialisé à `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, dont le vecteur stocké `subs` contient les valeurs `N` vers lesquelles pointe l’argument de constructeur `submatches`, et dont la valeur stockée `pos` est égale à zéro.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratorregextypea--regextokeniteratorregextype"></a><a name="regex_token_iterator__regex_type"></a>  regex_token_iterator::regex_type  
 Type de l’expression régulière à mettre en correspondance.  
  
```  
typedef basic_regex<Elem, RXtraits> regex_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme de `basic_regex<Elem, RXtraits>`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_regex_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
##  <a name="a-nameregextokeniteratorvaluetypea--regextokeniteratorvaluetype"></a><a name="regex_token_iterator__value_type"></a>  regex_token_iterator::value_type  
 Type d’une sous-correspondance.  
  
```  
typedef sub_match<BidIt> value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `sub_match<BidIt>`, où `BidIt` est le paramètre de modèle.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_token_iterator_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_token_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "aaxaayaaz";   
    Myiter::regex_type rx("(a)a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
// show whole match   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefix before match   
    next = Myiter(pat, pat + strlen(pat), rx, -1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show (a) submatch only   
    next = Myiter(pat, pat + strlen(pat), rx, 1);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and submatches   
    std::vector<int> vec;   
    vec.push_back(-1);   
    vec.push_back(1);   
    next = Myiter(pat, pat + strlen(pat), rx, vec);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
// show prefixes and whole matches   
    int arr[] = {-1, 0};   
    next = Myiter(pat, pat + strlen(pat), rx, arr);   
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
    std::cout << std::endl;   
  
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
match == aa  
match == aa  
match == aa  
  
match ==   
match == x  
match == y  
match == z  
  
match == a  
match == a  
match == a  
  
match ==   
match == a  
match == x  
match == a  
match == y  
match == a  
match == z  
  
match ==   
match == aa  
match == x  
match == aa  
match == y  
match == aa  
match == z  
  
```  
  
## <a name="see-also"></a>Voir aussi  
[\<regex>](../standard-library/regex.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[regex_error, classe](../standard-library/regex-error-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[\<regex>, opérateurs](../standard-library/regex-operators.md)  
[regex_traits, classe](../standard-library/regex-traits-class.md)  
[\<regex>, typedefs](../standard-library/regex-typedefs.md)  


