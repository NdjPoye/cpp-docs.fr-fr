---
title: regex_traits, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_traits
- regex/std::regex_traits
- regex/std::regex_traits::char_type
- regex/std::regex_traits::size_type
- regex/std::regex_traits::string_type
- regex/std::regex_traits::locale_type
- regex/std::regex_traits::char_class_type
- regex/std::regex_traits::length
- regex/std::regex_traits::translate
- regex/std::regex_traits::translate_nocase
- regex/std::regex_traits::transform
- regex/std::regex_traits::transform_primary
- regex/std::regex_traits::lookup_classname
- regex/std::regex_traits::lookup_collatename
- regex/std::regex_traits::isctype
- regex/std::regex_traits::value
- regex/std::regex_traits::imbue
- regex/std::regex_traits::getloc
dev_langs:
- C++
helpviewer_keywords:
- regex_traits class
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 19
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
ms.openlocfilehash: b41e9b019477fe86645a212ee9f345e0fe8685f7
ms.lasthandoff: 02/24/2017

---
# <a name="regextraits-class"></a>Classe regex_traits
Décrit les caractéristiques des éléments pour la mise en correspondance.  
  
## <a name="syntax"></a>Syntaxe  
```  
template<class Elem>
class regex_traits {  
public:  
   typedef Elem char_type;  
   typedef size_t size_type;  
   typedef basic_string<Elem> string_type;  
   typedef locale locale_type;  
   typedef ctype_base::mask char_class_type;  

   regex_traits();
   static size_type length(const char_type *str);
   char_type translate(char_type ch) const;
   char_type translate_nocase(char_type ch) const;
   template <class FwdIt>  
   string_type transform(FwdIt first, FwdIt last) const;
   template <class FwdIt>  
   string_type transform_primary(FwdIt first, FwdIt last) const;
   template <class FwdIt>  
   char_class_type lookup_classname(FwdIt first, FwdIt last) const;
   template <class FwdIt>  
   string_type lookup_collatename(FwdIt first, FwdIt last) const;
   bool isctype(char_type ch, char_class_type cls) const;
   int value(char_type ch, int base) const;
   locale_type imbue(locale_type loc);
   locale_type getloc() const;
};  
 ``` 
#### <a name="parameters"></a>Paramètres  
 `Elem`  
 Type d’élément caractère à décrire.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit différents traits d’expressions régulières pour le type `Elem`. La classe de modèle [basic_regex](../standard-library/basic-regex-class.md) utilise ces informations pour manipuler les éléments de type `Elem`.  
  
 Chaque objet `regex_traits` a un objet de type `regex_traits::locale` qui est utilisé par certaines de ses fonctions membres. Les paramètres régionaux par défaut sont une copie de `regex_traits::locale()`. La fonction membre `imbue` remplace l’objet de paramètres régionaux , et la fonction membre `getloc` retourne une copie de l’objet de paramètres régionaux.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<regex>  
  
 **Espace de noms :** std  
  
##  <a name="regex_traits__char_class_type"></a>  regex_traits::char_class_type  
 Type des désignateurs de classes de caractères.  
  
```  
typedef T8 char_class_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme pour un type non spécifique qui désigne les classes de caractères. Vous pouvez combiner les valeurs de ce type à l’aide de l’opérateur `|` pour désigner les classes de caractères qui représentent l’union des classes désignées par les opérandes.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_char_class_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__char_type"></a>  regex_traits::char_type  
 Type d’un élément.  
  
```  
typedef Elem char_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme de l'argument de modèle `Elem`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_char_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__getloc"></a>  regex_traits::getloc  
 Retourne l’objet des paramètres régionaux stockés.  
  
```  
locale_type getloc() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’objet `locale` stocké.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_getloc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__imbue"></a>  regex_traits::imbue  
 Modifie l’objet des paramètres régionaux stocké.  
  
```  
locale_type imbue(locale_type loc);
```  
  
### <a name="parameters"></a>Paramètres  
 `loc`  
 Objet de paramètres régionaux à stocker.  
  
### <a name="remarks"></a>Notes  
 La fonction membre copie `loc` vers l’objet `locale` stocké et retourne une copie de la valeur précédente de l’objet `locale` stocké.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_imbue.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__isctype"></a>  regex_traits::isctype  
 Teste l’appartenance à la classe.  
  
```  
bool isctype(char_type ch, char_class_type cls) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `ch`  
 Élément à tester.  
  
 `cls`  
 Classes à tester.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la valeur true uniquement si le caractère `ch` fait partie de la classe de caractères désignée par `cls`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_isctype.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__length"></a>  regex_traits::length  
 Retourne la longueur d’une séquence se terminant par un caractère Null.  
  
```  
static size_type length(const char_type *str);
```  
  
### <a name="parameters"></a>Paramètres  
 `str`  
 Séquence terminée par un caractère Null.  
  
### <a name="remarks"></a>Notes  
 La fonction membre statique retourne `std::char_traits<char_type>::length(str)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_length.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__locale_type"></a>  regex_traits::locale_type  
 Type de l’objet de paramètres régionaux stocké.  
  
```  
typedef T7 locale_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme d’un type qui encapsule les paramètres régionaux. Dans les spécialisations `regex_traits<char>` et `regex_traits<wchar_t>` , il s'agit d'un synonyme de `std::locale`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_locale_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__lookup_classname"></a>  regex_traits::lookup_classname  
 Mappe une séquence à une classe de caractères.  
  
```  
template <class FwdIt>  
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la séquence à rechercher.  
  
 `last`  
 Fin de la séquence à rechercher.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne une valeur qui désigne la classe de caractères nommée par la séquence de caractères vers laquelle pointent ses arguments. La valeur ne dépend pas de la casse des caractères dans la séquence.  
  
 La spécialisation `regex_traits<char>` reconnaît les noms `"d"`, `"s"`, `"w"`, `"alnum"`, `"alpha"`, `"blank"`, `"cntrl"`, `"digit"`, `"graph"`, `"lower"`, `"print"`, `"punct"`, `"space"`, `"upper"` et `"xdigit"`, tous sans respect de la casse.  
  
 La spécialisation `regex_traits<wchar_t>` reconnaît les noms `L"d"`, `L"s"`, `L"w"`, `L"alnum"`, `L"alpha"`, `L"blank"`, `L"cntrl"`, `L"digit"`, `L"graph"`, `L"lower"`, `L"print"`, `L"punct"`, `L"space"`, `L"upper"` et `L"xdigit"`, tous sans respect de la casse.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_lookup_classname.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__lookup_collatename"></a>  regex_traits::lookup_collatename  
 Mappe une séquence à un élément de classement.  
  
```  
template <class FwdIt>  
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la séquence à rechercher.  
  
 `last`  
 Fin de la séquence à rechercher.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne un objet string contenant l’élément de classement correspondant à la séquence `[first, last)`, ou une chaîne vide si la séquence n’est pas un élément de classement valide.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_lookup_collatename.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__regex_traits"></a>  regex_traits::regex_traits  
 Construit l’objet.  
  
```  
regex_traits();
```  
  
### <a name="remarks"></a>Notes  
 Le constructeur construit un objet dont l'objet `locale` stocké est initialisé avec les paramètres régionaux par défaut.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__size_type"></a>  regex_traits::size_type  
 Type d'une longueur de séquence.  
  
```  
typedef T6 size_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme d'un type intégral non signé. Dans les spécialisations `regex_traits<char>` et `regex_traits<wchar_t>`, il s'agit d'un synonyme de `std::size_t`.  
  
 Le typedef est un synonyme de `std::size_t`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_size_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__string_type"></a>  regex_traits::string_type  
 Type d'une chaîne d'éléments.  
  
```  
typedef basic_string<Elem> string_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme de `basic_string<Elem>`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_string_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__transform"></a>  regex_traits::transform  
 Convertit en séquence ordonnée équivalente.  
  
```  
template <class FwdIt>  
string_type transform(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la séquence à transformer.  
  
 `last`  
 Fin de la séquence à transformer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne une chaîne qu’elle génère à l’aide d’une règle de transformation qui dépend de l’objet `locale` stocké. Pour deux séquences de caractères désignées par les plages d’itérateurs `[first1, last1)` et `[first2, last2)`, `transform(first1, last1) < transform(first2, last2)` si la séquence de caractères désignée par la plage d’itérateurs `[first1, last1)` est triée avant la séquence de caractères désignée par la plage d’itérateurs `[first2, last2)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_transform.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__transform_primary"></a>  regex_traits::transform_primary  
 Convertit en séquence ordonnée équivalente ne respectant pas la casse.  
  
```  
template <class FwdIt>  
string_type transform_primary(FwdIt first, FwdIt last) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la séquence à transformer.  
  
 `last`  
 Fin de la séquence à transformer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne une chaîne qu’elle génère à l’aide d’une règle de transformation qui dépend de l’objet `locale` stocké. Pour deux séquences de caractères désignées par les plages d’itérateurs `[first1, last1)` et `[first2, last2)`, `transform_primary(first1, last1) < transform_primary(first2, last2)` si la séquence de caractères désignée par la plage d’itérateurs `[first1, last1)` est triée avant la séquence de caractères désignée par la plage d’itérateurs `[first2, last2)` indépendamment de la casse ou des accents.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_transform_primary.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__translate"></a>  regex_traits::translate  
 Convertit en un élément correspondant équivalent.  
  
```  
char_type translate(char_type ch) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `ch`  
 Élément à convertir.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne un caractère qu’elle génère à l’aide d’une règle de transformation qui dépend de l’objet `locale` stocké. Pour deux objets `char_type` `ch1` et `ch2`, `translate(ch1) == translate(ch2)` seulement si `ch1` et `ch2` doivent correspondre quand un des objets est présent dans la définition de l’expression régulière et que l’autre se trouve à la position correspondante dans la séquence cible pour une correspondance respectant les paramètres régionaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_translate.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__translate_nocase"></a>  regex_traits::translate_nocase  
 Convertit en un élément correspondant équivalent ne respectant pas la casse.  
  
```  
char_type translate_nocase(char_type ch) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `ch`  
 Élément à convertir.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne un caractère qu’elle génère à l’aide d’une règle de transformation qui dépend de l’objet `locale` stocké. Pour deux objets `char_type` `ch1` et `ch2`, `translate_nocase(ch1) == translate_nocase(ch2)` seulement si `ch1` et `ch2` doivent correspondre quand un des objets est présent dans la définition de l’expression régulière et que l’autre se trouve à la position correspondante dans la séquence cible pour une correspondance ne respectant pas la casse.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_translate_nocase.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
##  <a name="regex_traits__value"></a>  regex_traits::value  
 Convertit un élément en valeur numérique.  
  
```  
int value(Elem ch, int radix) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `ch`  
 Élément à convertir.  
  
 `radix`  
 Base arithmétique à utiliser.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la valeur représentée par le caractère `ch` dans la base `radix`, ou -1 si `ch` n’est pas un chiffre valide dans la base `radix`. La fonction est uniquement appelée avec un argument `radix` dont la valeur est 8, 10 ou 16.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__regex__regex_traits_value.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_traits<char> Mytr;   
int main()   
    {   
    Mytr tr;   
  
    Mytr::char_type ch = tr.translate('a');   
    std::cout << "translate('a') == 'a' == " << std::boolalpha   
        << (ch == 'a') << std::endl;   
  
    std::cout << "nocase 'a' == 'A' == " << std::boolalpha   
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))   
        << std::endl;   
  
    const char *lbegin = "abc";   
    const char *lend = lbegin + strlen(lbegin);   
    Mytr::size_type size = tr.length(lbegin);   
    std::cout << "length(\"abc\") == " << size <<std::endl;   
  
    Mytr::string_type str = tr.transform(lbegin, lend);   
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha   
        << (str < "abc") << std::endl;   
  
    const char *ubegin = "ABC";   
    const char *uend = ubegin + strlen(ubegin);   
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha   
        << (tr.transform_primary(ubegin, uend) <   
            tr.transform_primary(lbegin, lend))   
        << std::endl;   
  
    const char *dig = "digit";   
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);   
    std::cout << "class digit == d == " << std::boolalpha   
        << (cl == tr.lookup_classname(dig, dig + 1))   
        << std::endl;   
  
    std::cout << "'3' is digit == " <<std::boolalpha   
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))   
        << std::endl;   
  
    std::cout << "hex C == " << tr.value('C', 16) << std::endl;   
  
// other members   
    str = tr.lookup_collatename(dig, dig + 5);   
  
    Mytr::locale_type loc = tr.getloc();   
    tr.imbue(loc);   
  
    return (0);   
    }  
  
```  
  
```Output  
translate('a') == 'a' == true  
nocase 'a' == 'A' == true  
length("abc") == 3  
transform("abc") < "abc" == false  
primary "ABC" < "abc" == false  
class digit == d == true  
'3' is digit == true  
hex C == 12  
```  
  
## <a name="see-also"></a>Voir aussi  
[\<regex>](../standard-library/regex.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[regex_error, classe](../standard-library/regex-error-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[\<regex>, opérateurs](../standard-library/regex-operators.md)  
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)  
[\<regex>, typedefs](../standard-library/regex-typedefs.md)  
 [regex_traits\<char>, classe](../standard-library/regex-traits-char-class.md)   
 [regex_traits\<wchar_t>, classe](../standard-library/regex-traits-wchar-t-class.md)


