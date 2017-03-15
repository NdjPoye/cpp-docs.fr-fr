---
title: "&lt;istream&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4c2a2f8c2c2b55e3c14db9e44a4b05041c0ecfc9
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt;, opérateurs
 
##  <a name="a-nameoperatorgtgta--operatorgtgt"></a><a name="operator_gt__gt_"></a>  operator&gt;&gt;  
 Extrait des chaînes et des caractères à partir du flux.  
  
```  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem* str);

template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char& Ch);

template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `Ch`  
 Un caractère.  
  
 `Istr`  
 Flux.  
  
 ` str`  
 Chaîne.  
  
 ` val`  
 Type.  
  
### <a name="return-value"></a>Valeur de retour  
 Flux.  
  
### <a name="remarks"></a>Notes  
 La classe `basic_istream` définit également plusieurs opérateurs d’extraction. Pour plus d’informations, consultez [basic_istream::operator>>](../standard-library/basic-istream-class.md#basic_istream__operator_gt__gt_).  
  
 La fonction de modèle :  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```  
  
 extrait jusqu’à *N* - 1 éléments et les stocke dans le tableau en commençant à _ *Str*. Si `Istr`. [width](../standard-library/ios-base-class.md#ios_base__width) est supérieure à zéro, *N* est `Istr`. **width**. Sinon, il est égal à la taille du plus grand tableau **Elem** qui peut être déclaré. La fonction stocke toujours la valeur **Elem()** après tout élément extrait qu’elle stocke. L’extraction s’arrête dès la fin du fichier, sur un caractère avec la valeur **Elem**(0) (qui n’est pas extrait), ou sur tout élément (qui n’est pas extrait) qui serait ignoré par [ws](../standard-library/istream-functions.md#ws). Si la fonction n’extrait aucun élément, elle appelle `Istr`. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Dans tous les cas, elle appelle `Istr`. **width**(0) et retourne `Istr`.  
  
 **Note de sécurité** La chaîne terminée par Null qui est extraite du flux d’entrée ne doit pas dépasser la taille de la mémoire tampon de destination ` str`. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 La fonction de modèle :  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```  
  
 extrait un élément, si c’est possible, et le stocke dans `Ch`. Sinon, elle appelle **is**. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Dans tous les cas, elle retourne `Istr`.  
  
 La fonction de modèle :  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```  
  
 retourne `Istr` >> ( `char`**\***) ` str`.  
  
 La fonction de modèle :  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```  
  
 retourne `Istr` >> ( **char&**) `Ch`.  
  
 La fonction de modèle :  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```  
  
 retourne `Istr` >> ( **char \***) ` str`.  
  
 La fonction de modèle :  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```  
  
 retourne `Istr` >> ( **char&**) `Ch`.  
  
 La fonction de modèle :  
  
```cpp  
template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
 retourne `Istr` `>>` ` val` (et convertit un `rvalue reference` à `Istr` en un `lvalue` dans le même temps).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_op_extract.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   ws( cin );  
   char c[10];  
  
   cin.width( 9 );  
   cin >> c;  
   cout << c << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<istream>](../standard-library/istream.md)


