---
title: "&lt;string&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 31a7a65ed759ec552e11f2eccc5d425c2b2b765d
ms.openlocfilehash: 3772b1a90b699d2deb6a573c54b802122109fbf1
ms.lasthandoff: 02/24/2017

---
# <a name="ltstringgt-operators"></a>&lt;string&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;&gt;](#operator_gt__gt_)|  
|[operator&gt;=](#operator_gt__eq)|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|  
|[operator&lt;=](#operator_lt__eq)|[operator+](#operator_add)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatoradda--operator"></a><a name="operator_add"></a>  operator+  
 Concatène deux objets string.  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const CharType right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    CharType right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,  
    const basic_string<CharType, Traits, Allocator>&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à concaténer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à concaténer.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne qui est la concaténation des chaînes d'entrée.  
  
### <a name="remarks"></a>Notes  
 Les fonctions surchargent toutes `operator+` pour concaténer deux objets de classe de modèle [basic_string](../standard-library/basic-string-class.md). Elles retournent toutes `basic_string`\< **CharType**, **Traits**, **Allocator**>(_ *Left*). [append](../standard-library/basic-string-class.md#basic_string__append)(\_ *Right*).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_con.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // Declaring an object of type basic_string<char>  
   string s1 ( "anti" );  
   string s2 ( "gravity" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "heroine";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // Declaring a character constant  
   char c1 = '!';  
   cout << "The character constant c1 = " << c1 << "." << endl;  
  
   // First member function: concatenates an  object  
   // of type basic_string with an object of type basic_string  
   string s12 = s1 + s2;  
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;  
  
   // Second & fourth member functions: concatenate an object  
   // of type basic_string with an object of C-syle string type  
   string s1s3 = s1 + s3;  
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;  
  
   // Third & fifth member functions: concatenate an object  
   // of type basic_string with a character constant  
   string s1s3c1 = s1s3 + c1;  
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;  
}  
```  
  
```Output  
The basic_string s1 = anti.  
The basic_string s2 = gravity.  
The C-style string s3 = heroine.  
The character constant c1 = !.  
The string concatenating s1 & s2 is: antigravity  
The string concatenating s1 & s3 is: antiheroine  
The string concatenating s1 & s3 is: antiheroine!  
```  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Teste si l'objet string situé à gauche de l'opérateur n'est pas égal à l'objet string situé à droite.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left, 
const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet string situé à gauche de l’opérateur n’est pas égal du point de vue lexicographique à l’objet string situé à droite ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets string est basée sur une comparaison lexicographique par paire de leurs caractères. Deux chaînes sont égales si elles ont le même nombre de caractères et que les valeurs respectives de leurs caractères sont identiques. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_ne.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "pluck" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "pluck";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 != s2 )  
      cout << "The strings s1 & s2 are not equal." << endl;  
   else  
      cout << "The strings s1 & s2 are equal." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 != s3 )  
      cout << "The strings s1 & s3 are not equal." << endl;  
   else  
      cout << "The strings s1 & s3 are equal." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s3 != s2 )  
      cout << "The strings s3 & s2 are not equal." << endl;  
   else  
      cout << "The strings s3 & s2 are equal." << endl;  
}  
```  
  
```Output  
The basic_string s1 = pluck.  
The basic_string s2 = strum.  
The C-style string s3 = pluck.  
The strings s1 & s2 are not equal.  
The strings s1 & s3 are equal.  
The strings s3 & s2 are not equal.  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Teste si l'objet string situé à gauche de l'opérateur est égal à l'objet string situé à droite.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator==(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet string situé à gauche de l’opérateur est égal du point de vue lexicographique à l’objet string situé à droite ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets string est basée sur une comparaison lexicographique par paire de leurs caractères. Deux chaînes sont égales si elles ont le même nombre de caractères et que les valeurs respectives de leurs caractères sont identiques. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_eq.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "pluck" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "pluck";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 == s2 )  
      cout << "The strings s1 & s2 are equal." << endl;  
   else  
      cout << "The strings s1 & s2 are not equal." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 == s3 )  
      cout << "The strings s1 & s3 are equal." << endl;  
   else  
      cout << "The strings s1 & s3 are not equal." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s3 == s2 )  
      cout << "The strings s3 & s2 are equal." << endl;  
   else  
      cout << "The strings s3 & s2 are not equal." << endl;  
}  
```  
  
```Output  
The basic_string s1 = pluck.  
The basic_string s2 = strum.  
The C-style string s3 = pluck.  
The strings s1 & s2 are not equal.  
The strings s1 & s3 are equal.  
The strings s3 & s2 are not equal.  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 Teste si l'objet string situé à gauche de l'opérateur est inférieur à l'objet string situé à droite.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator<(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet string situé à gauche de l’opérateur est inférieur du point de vue lexicographique à l’objet string situé à droite ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes les compare caractère par caractère jusqu’à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_lt.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "strict";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 < s2 )  
      cout << "The string s1 is less than the string s2." << endl;  
   else  
      cout << "The string s1 is not less than the string s2." << endl;  
  
   // Second member function: comparison between left-hand object  
   // of type basic_string & right-hand object of C-syle string type  
   if ( s1 < s3 )  
      cout << "The string s1 is less than the string s3." << endl;  
   else  
      cout << "The string s1 is not less than the string s3." << endl;  
  
   // Third member function: comparison between left-hand object  
   // of C-syle string type & right-hand object of type basic_string  
   if ( s3 < s2 )  
      cout << "The string s3 is less than the string s2." << endl;  
   else  
      cout << "The string s3 is not less than the string s2." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = strict.  
The string s1 is less than the string s2.  
The string s1 is not less than the string s3.  
The string s3 is less than the string s2.  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 Teste si l'objet string situé à gauche de l'opérateur est inférieur ou égal à l'objet string situé à droite.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet string situé à gauche de l’opérateur est inférieur ou égal du point de vue lexicographique à l’objet string situé à droite ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes les compare caractère par caractère jusqu’à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_le.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "strict";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 <= s2 )  
      cout << "The string s1 is less than or equal to "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is greater than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 <= s3 )  
      cout << "The string s1 is less than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s1 is greater than "  
           << "the string s3." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type  & right-side object of type basic_string  
   if ( s2 <= s3 )  
      cout << "The string s2 is less than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is greater than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = strict.  
The string s1 is less than or equal to the string s2.  
The string s1 is less than or equal to the string s3.  
The string s2 is greater than the string s3.  
```  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 Fonction de modèle qui écrit une chaîne dans le flux de sortie.  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr, 
    const basic_string<CharType, Traits, Allocator>& str);
```  
  
### <a name="parameters"></a>Paramètres  
 _Ostr  
 Flux de sortie dans lequel s’effectue l’écriture.  
  
 ` str`  
 Chaîne à entrer dans le flux de sortie.  
  
### <a name="return-value"></a>Valeur de retour  
 Écrit la valeur de la chaîne spécifiée dans le flux de sortie `_Ostr`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle surcharge **operator<<** pour insérer un objet _ *Str* de classe de modèle [basic_string](../standard-library/basic-string-class.md) dans le flux \_ *Ostr.* La fonction retourne effectivement \_ *Ostr*. **write**( \_ *Str*. [c_str](../standard-library/basic-string-class.md#basic_string__c_str), \_ *Str*. [size](../standard-library/basic-string-class.md#basic_string__size)).  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 Teste si l'objet string situé à gauche de l'opérateur est supérieur à l'objet string situé à droite.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator>(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet string situé à gauche de l’opérateur est supérieur du point de vue lexicographique à l’objet string situé à droite ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes les compare caractère par caractère jusqu’à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_gt.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "stricture";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 > s2 )  
      cout << "The string s1 is greater than "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is not greater than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s3 > s1 )  
      cout << "The string s3 is greater than "  
           << "the string s1." << endl;  
   else  
      cout << "The string s3 is not greater than "  
           << "the string s1." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s2 > s3 )  
      cout << "The string s2 is greater than "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is not greater than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = stricture.  
The string s1 is not greater than the string s2.  
The string s3 is greater than the string s1.  
The string s2 is greater than the string s3.  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 Teste si l'objet string situé à gauche de l'opérateur est supérieur ou égal à l'objet string situé à droite.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
 ` right`  
 Chaîne de style C ou objet de type `basic_string` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet string situé à gauche de l’opérateur est supérieur ou égal du point de vue lexicographique à l’objet string situé à droite ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes les compare caractère par caractère jusqu’à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_ge.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "stricture";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 >= s2 )  
      cout << "The string s1 is greater than or equal to "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is less than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s3 >= s1 )  
      cout << "The string s3 is greater than or equal to "  
           << "the string s1." << endl;  
   else  
      cout << "The string s3 is less than "  
           << "the string s1." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s2 >= s3 )  
      cout << "The string s2 is greater than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is less than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = stricture.  
The string s1 is less than the string s2.  
The string s3 is greater than or equal to the string s1.  
The string s2 is greater than or equal to the string s3.  
```  
  
##  <a name="a-nameoperatorgtgta--operatorgtgt"></a><a name="operator_gt__gt_"></a>  operator&gt;&gt;  
 Fonction de modèle qui lit une chaîne à partir d’un flux d’entrée.  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,  
    basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Istr`  
 Le flux d’entrée utilisé pour extraire la séquence.  
  
 ` right`  
 La chaîne qui est extraite du flux d’entrée.  
  
### <a name="return-value"></a>Valeur de retour  
 Lit la valeur de la chaîne spécifiée à partir de `_Istr` et la retourne dans ` right.`  
  
### <a name="remarks"></a>Notes  
 L’opérateur ignore les espaces blancs de début à moins que l’indicateur `skipws` soit défini. Il lit tous les caractères suivants jusqu’à ce que le caractère suivant soit un espace blanc ou que la fin du fichier soit atteinte.  
  
 La fonction de modèle surcharge **operator>>** pour remplacer la séquence contrôlée par ` right` avec une séquence d’éléments extraits à partir du flux `_Istr`. L’extraction s’arrête :  
  
-   À la fin du fichier.  
  
-   Une fois que la fonction a extrait `_Istr`. **width** éléments, si cette valeur est différente de zéro.  
  
 Une fois que la fonction a extrait `_Istr`. [max_size](../standard-library/basic-string-class.md#basic_string__max_size) éléments.  
  
-   Une fois que la fonction a extrait un élément *ch* pour lequel [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **CharType**> >( `getloc`). **is**( **ctype**\< **CharType**>:: **space**, *ch*) a la valeur true, auquel cas le caractère est replacé.  
  
 Si la fonction n’extrait aucun élément, elle appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( `ios_base::failbit`). Dans tous les cas, elle appelle **istr**. **width**(0) et retourne \* **this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// string_op_read_.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   string c0;  
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";  
   cin >> c0;  
   cout << "The string entered is c0 = " << c0 << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<string>](../standard-library/string.md)

