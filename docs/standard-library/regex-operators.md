---
title: "&lt;regex&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::operator!=
- regex/std::operator>
- regex/std::operator>=
- regex/std::operator<
- regex/std::operator<=
- regex/std::operator==
- regex/std::operator<<
ms.assetid: ec623e65-c186-491f-aa18-6b12b47e1127
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 254eee6065dfc4b11c6eadf82d07fcfb5a7cf4e3
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt-operators"></a>&lt;regex&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Comparaison « n’est pas égal à » entre plusieurs objets.  
  
```  
template <class BidIt>  
bool operator!=(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator!=(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator!=(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator!=(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator!=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator!=(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator!=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);

template <class BidIt, class Alloc>  
bool operator!=(const match_results<BidIt, Alloc>& left,  
    const match_results<BidIt, Alloc>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `left`  
 Objet de gauche à comparer.  
  
 `right`  
 Objet de droite à comparer.  
  
### <a name="remarks"></a>Notes  
 Chaque opérateur de modèle retourne `!(left == right)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "match == " << mr.str() << std::endl;   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "match != match == " << std::boolalpha   
        << (mr != mr) << std::endl;   
    std::cout << "sub != sub == " << std::boolalpha   
        << (sub != sub) << std::endl;   
  
    std::cout << "string(\"aab\") != sub == " << std::boolalpha   
        << (Mystr("aab") != sub) << std::endl;   
    std::cout << "sub != string(\"aab\") == " << std::boolalpha   
        << (sub != Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" != sub == " << std::boolalpha   
        << ("aab" != sub) << std::endl;   
    std::cout << "sub != \"aab\" == " << std::boolalpha   
        << (sub != "aab") << std::endl;   
  
    std::cout << "'a' != sub == " << std::boolalpha   
        << ('a' != sub) << std::endl;   
    std::cout << "sub != 'a' == " << std::boolalpha   
        << (sub != 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == caaa  
sub == aaa  
  
match != match == false  
sub != sub == false  
string("aab") != sub == true  
sub != string("aab") == true  
"aab" != sub == true  
sub != "aab" == true  
'a' != sub == true  
sub != 'a' == true  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 Comparaison « inférieur à » entre plusieurs objets.  
  
```  
template <class BidIt>  
bool operator<(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator<(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator<(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `left`  
 Objet de gauche à comparer.  
  
 `right`  
 Objet de droite à comparer.  
  
### <a name="remarks"></a>Notes  
 Chaque opérateur de modèle convertit ses arguments en type chaîne et retourne true uniquement si la comparaison indique que la valeur convertie de `left` est inférieure à la valeur convertie de `right`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_lt.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub < sub == " << std::boolalpha   
        << (sub < sub) << std::endl;   
  
    std::cout << "string(\"aab\") < sub == " << std::boolalpha   
        << (Mystr("aab") < sub) << std::endl;   
    std::cout << "sub < string(\"aab\") == " << std::boolalpha   
        << (sub < Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" < sub == " << std::boolalpha   
        << ("aab" < sub) << std::endl;   
    std::cout << "sub < \"aab\" == " << std::boolalpha   
        << (sub < "aab") << std::endl;   
  
    std::cout << "'a' < sub == " << std::boolalpha   
        << ('a' < sub) << std::endl;   
    std::cout << "sub < 'a' == " << std::boolalpha   
        << (sub < 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sub == aaa  
  
sub < sub == false  
string("aab") < sub == false  
sub < string("aab") == true  
"aab" < sub == false  
sub < "aab" == true  
'a' < sub == true  
sub < 'a' == false  
```  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 Insère un sub_match dans un flux.  
  
```  
template <class Elem, class IOtraits, class Alloc, class BidIt>  
basic_ostream<Elem, IOtraits>& operator<<(basic_ostream<Elem, IOtraits>& os,  
    const sub_match<BidIt>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Elem`  
 Type de l’élément.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `BidIt`  
 Type d'itérateur.  
  
 `os`  
 Flux de sortie.  
  
 `right`  
 Objet à insérer.  
  
### <a name="remarks"></a>Notes  
 L’opérateur de modèle retourne `os << right.str()`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_ins.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[0];   
    std::cout << "whole match: " << sub << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
whole match: caaa  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 Comparaison « inférieur ou égal à » entre plusieurs objets.  
  
```  
template <class BidIt>  
bool operator<=(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<=(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<=(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator<=(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator<=(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `left`  
 Objet de gauche à comparer.  
  
 `right`  
 Objet de droite à comparer.  
  
### <a name="remarks"></a>Notes  
 Chaque opérateur de modèle retourne `!(right < left)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_le.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub <= sub == " << std::boolalpha   
        << (sub <= sub) << std::endl;   
  
    std::cout << "string(\"aab\") <= sub == " << std::boolalpha   
        << (Mystr("aab") <= sub) << std::endl;   
    std::cout << "sub <= string(\"aab\") == " << std::boolalpha   
        << (sub <= Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" <= sub == " << std::boolalpha   
        << ("aab" <= sub) << std::endl;   
    std::cout << "sub <= \"aab\" == " << std::boolalpha   
        << (sub <= "aab") << std::endl;   
  
    std::cout << "'a' <= sub == " << std::boolalpha   
        << ('a' <= sub) << std::endl;   
    std::cout << "sub <= 'a' == " << std::boolalpha   
        << (sub <= 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sub == aaa  
  
sub <= sub == true  
string("aab") <= sub == false  
sub <= string("aab") == true  
"aab" <= sub == false  
sub <= "aab" == true  
'a' <= sub == true  
sub <= 'a' == false  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Comparaison « est égal à » entre plusieurs objets.  
  
```  
template <class BidIt>  
bool operator==(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator==(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator==(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator==(const typename iterator_traits<BidIt>::value_type* left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator==(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type* right);

template <class BidIt>  
bool operator==(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator==(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);

template <class BidIt, class Alloc>  
bool operator==(const match_results<BidIt, Alloc>& left,  
    const match_results<BidIt, Alloc>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `left`  
 Objet de gauche à comparer.  
  
 `right`  
 Objet de droite à comparer.  
  
### <a name="remarks"></a>Notes  
 Chaque opérateur de modèle convertit chacun de ses arguments en type chaîne et retourne le résultat de la comparaison d’égalité entre les objets convertis.  
  
 Quand un opérateur de modèle convertit ses arguments en type chaîne, il utilise la première des transformations suivantes qui s’applique :  
  
 les arguments dont les types sont une spécialisation de la classe de modèle `match_results` ou `sub_match` sont convertis en appelant la fonction membre `str` ;  
  
 les arguments dont les types sont une spécialisation de la classe de modèle `basic_string` restent inchangés ;  
  
 tous les autres types d’arguments sont convertis en passant la valeur d’argument au constructeur pour une spécialisation appropriée de la classe de modèle `basic_string`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_eq.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "match == " << mr.str() << std::endl;   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "match == match == " << std::boolalpha   
        << (mr == mr) << std::endl;   
    std::cout << "sub == sub == " << std::boolalpha   
        << (sub == sub) << std::endl;   
  
    std::cout << "string(\"aab\") == sub == " << std::boolalpha   
        << (Mystr("aab") == sub) << std::endl;   
    std::cout << "sub == string(\"aab\") == " << std::boolalpha   
        << (sub == Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" == sub == " << std::boolalpha   
        << ("aab" == sub) << std::endl;   
    std::cout << "sub == \"aab\" == " << std::boolalpha   
        << (sub == "aab") << std::endl;   
  
    std::cout << "'a' == sub == " << std::boolalpha   
        << ('a' == sub) << std::endl;   
    std::cout << "sub == 'a' == " << std::boolalpha   
        << (sub == 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == caaa  
sub == aaa  
  
match == match == true  
sub == sub == true  
string("aab") == sub == false  
sub == string("aab") == false  
"aab" == sub == false  
sub == "aab" == false  
'a' == sub == false  
sub == 'a' == false  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 Comparaison « supérieur à » entre plusieurs objets.  
  
```  
template <class BidIt>  
bool operator>(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator>(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator>(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `left`  
 Objet de gauche à comparer.  
  
 `right`  
 Objet de droite à comparer.  
  
### <a name="remarks"></a>Notes  
 Chaque opérateur de modèle retourne `right < left`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_gt.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub > sub == " << std::boolalpha   
        << (sub > sub) << std::endl;   
  
    std::cout << "string(\"aab\") > sub == " << std::boolalpha   
        << (Mystr("aab") > sub) << std::endl;   
    std::cout << "sub > string(\"aab\") == " << std::boolalpha   
        << (sub > Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" > sub == " << std::boolalpha   
        << ("aab" > sub) << std::endl;   
    std::cout << "sub > \"aab\" == " << std::boolalpha   
        << (sub > "aab") << std::endl;   
  
    std::cout << "'a' > sub == " << std::boolalpha   
        << ('a' > sub) << std::endl;   
    std::cout << "sub > 'a' == " << std::boolalpha   
        << (sub > 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sub == aaa  
  
sub > sub == false  
string("aab") > sub == true  
sub > string("aab") == false  
"aab" > sub == true  
sub > "aab" == false  
'a' > sub == false  
sub > 'a' == true  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 Comparaison « supérieur ou égal à » entre plusieurs objets.  
  
```  
template <class BidIt>  
bool operator>=(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>=(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>=(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator>=(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator>=(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `BidIt`  
 Type d'itérateur.  
  
 `IOtraits`  
 Classe de caractéristiques des chaînes.  
  
 `Alloc`  
 Classe allocator.  
  
 `left`  
 Objet de gauche à comparer.  
  
 `right`  
 Objet de droite à comparer.  
  
### <a name="remarks"></a>Notes  
 Chaque opérateur de modèle retourne `!(left < right)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__operator_ge.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub >= sub == " << std::boolalpha   
        << (sub >= sub) << std::endl;   
  
    std::cout << "string(\"aab\") >= sub == " << std::boolalpha   
        << (Mystr("aab") >= sub) << std::endl;   
    std::cout << "sub >= string(\"aab\") == " << std::boolalpha   
        << (sub >= Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" >= sub == " << std::boolalpha   
        << ("aab" >= sub) << std::endl;   
    std::cout << "sub >= \"aab\" == " << std::boolalpha   
        << (sub >= "aab") << std::endl;   
  
    std::cout << "'a' >= sub == " << std::boolalpha   
        << ('a' >= sub) << std::endl;   
    std::cout << "sub >= 'a' == " << std::boolalpha   
        << (sub >= 'a') << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
sub == aaa  
  
sub >= sub == true  
string("aab") >= sub == true  
sub >= string("aab") == false  
"aab" >= sub == true  
sub >= "aab" == false  
'a' >= sub == false  
sub >= 'a' == true  
```  
  
## <a name="see-also"></a>Voir aussi  
[\<regex>](../standard-library/regex.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[regex_error, classe](../standard-library/regex-error-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)  
[regex_traits, classe](../standard-library/regex-traits-class.md)  
[\<regex>, typedefs](../standard-library/regex-typedefs.md)  


