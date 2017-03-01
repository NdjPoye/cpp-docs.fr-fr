---
title: "array, classe (Bibliothèque C++ Standard)| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array
- std::array
- array/std::array
- std::array::const_iterator
- array/std::array::const_iterator
- std::array::const_pointer
- array/std::array::const_pointer
- std::array::const_reference
- array/std::array::const_reference
- std::array::const_reverse_iterator
- array/std::array::const_reverse_iterator
- std::array::difference_type
- array/std::array::difference_type
- std::array::iterator
- array/std::array::iterator
- std::array::pointer
- array/std::array::pointer
- std::array::reference
- array/std::array::reference
- std::array::reverse_iterator
- array/std::array::reverse_iterator
- std::array::size_type
- array/std::array::size_type
- std::array::value_type
- array/std::array::value_type
- std::array::assign
- array/std::array::assign
- std::array::at
- array/std::array::at
- std::array::back
- array/std::array::back
- std::array::begin
- array/std::array::begin
- std::array::cbegin
- array/std::array::cbegin
- std::array::cend
- array/std::array::cend
- std::array::crbegin
- array/std::array::crbegin
- std::array::crend
- array/std::array::crend
- std::array::data
- array/std::array::data
- std::array::empty
- array/std::array::empty
- std::array::end
- array/std::array::end
- std::array::fill
- array/std::array::fill
- std::array::front
- array/std::array::front
- std::array::max_size
- array/std::array::max_size
- std::array::rbegin
- array/std::array::rbegin
- std::array::rend
- array/std::array::rend
- std::array::size
- array/std::array::size
- std::array::swap
- array/std::array::swap
- std::array::operator=
- array/std::array::operator=
- std::array::operator[]
- array/std::array::operator[]
dev_langs:
- C++
helpviewer_keywords:
- array class
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: 22
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0e5e79e423d268da61ac9062edd099330f742b59
ms.lasthandoff: 02/24/2017

---
# <a name="array-class-c-standard-library"></a>array, classe (Bibliothèque C++ standard)
Décrit un objet qui contrôle une séquence de longueur `N` constituée d'éléments de type `Ty`. La séquence est stockée comme tableau de `Ty`, contenu dans l'objet `array<Ty, N>`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty, std::size_t N>  
class array;  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Ty`|Type d’un élément.|  
|`N`|Nombre d'éléments.|  
  
## <a name="members"></a>Membres  
  
|||  
|-|-|  
|Définition de types|Description|  
|[array::const_iterator](#array__const_iterator)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[array::const_pointer](#array__const_pointer)|Type d'un pointeur constant vers un élément.|  
|[array::const_reference](#array__const_reference)|Type d'une référence constante à un élément.|  
|[array::const_reverse_iterator](#array__const_reverse_iterator)|Type d'un itérateur inserve constant pour la séquence contrôlée.|  
|[array::difference_type](#array__difference_type)|Type d'une distance signée entre deux éléments.|  
|[array::iterator](#array__iterator)|Type d'un itérateur pour la séquence contrôlée.|  
|[array::pointer](#array__pointer)|Type d'un pointeur vers un élément.|  
|[array::reference](#array__reference)|Type d'une référence à un élément.|  
|[array::reverse_iterator](#array__reverse_iterator)|Type d'un itérateur inverse pour la séquence contrôlée.|  
|[array::size_type](#array__size_type)|Type d'une distance non signée entre deux éléments.|  
|[array::value_type](#array__value_type)|Type d’un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[array::array](#array__array)|Construit un objet tableau.|  
|[array::assign](#array__assign)|Remplace tous les éléments.|  
|[array::at](#array__at)|Accède à un élément à une position spécifiée.|  
|[array::back](#array__back)|Accède au dernier élément.|  
|[array::begin](#array__begin)|Désigne le début de la séquence contrôlée.|  
|[array::cbegin](#array__cbegin)|Retourne un itérateur const à accès aléatoire pointant vers le premier élément du tableau.|  
|[array::cend](#array__cend)|Retourne un itérateur à accès aléatoire qui pointe juste après la fin du tableau.|  
|[array::crbegin](#array__crbegin)|Retourne un itérateur const qui traite le premier élément d'un tableau inversé.|  
|[array::crend](#array__crend)|Retourne un itérateur const qui pointe vers la fin d'un tableau inversé.|  
|[array::data](#array__data)|Obtient l'adresse du premier élément.|  
|[array::empty](#array__empty)|Vérifie la présence d'éléments.|  
|[array::end](#array__end)|Désigne la fin de la séquence contrôlée.|  
|[array::fill](#array__fill)|Remplace tous les éléments par une valeur spécifiée.|  
|[array::front](#array__front)|Accède au premier élément.|  
|[array::max_size](#array__max_size)|Compte le nombre d'éléments.|  
|[array::rbegin](#array__rbegin)|Désigne le début de la séquence contrôlée inverse.|  
|[array::rend](#array__rend)|Désigne la fin de la séquence contrôlée inverse.|  
|[array::size](#array__size)|Compte le nombre d'éléments.|  
|[array::swap](#array__swap)|Échange le contenu de deux conteneurs.|  
  
|||  
|-|-|  
|Opérateur|Description|  
|[array::operator=](#array__operator_eq)|Remplace la séquence contrôlée.|  
|[array::operator[]](#array__operator_at)|Accède à un élément à une position spécifiée.|  
  
## <a name="remarks"></a>Notes  
 Le type a un constructeur par défaut `array()` et un opérateur d'assignation par défaut `operator=`, et il satisfait aux conditions requises pour un `aggregate`. Par conséquent, les objets de type `array<Ty, N>` peuvent être initialisés à l'aide d'un initialiseur d'agrégat. Par exemple :  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 crée l'objet `ai` qui contient quatre valeurs entières, initialise les trois premiers éléments respectivement aux valeurs 1, 2 et 3, et initialise le quatrième élément à la valeur 0.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<array>  
  
 **Espace de noms :** std  
  
##  <a name="a-namearrayarraya--arrayarray"></a><a name="array__array"></a>  array::array  
 Construit un objet tableau.  
  
```  
array();

array(const array& right);
```  
  
### <a name="parameters"></a>Paramètres  
*right*  
 Objet ou plage à insérer.  
  
### <a name="remarks"></a>Notes  
Le constructeur par défaut `array()` laisse la séquence contrôlée non initialisée (ou initialisée par défaut). Vous l’utilisez pour spécifier une séquence contrôlée non initialisée.  
  
Le constructeur de copie `array(const array& right)` initialise la séquence contrôlée par la séquence [*right*`.begin()`, *right*`.end()`). Vous l’utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par l’objet tableau *right*.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_array.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1(c0);   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
##  <a name="a-namearrayassigna--arrayassign"></a><a name="array__assign"></a>  array::assign  
Obsolète dans C++11, remplacé par [fill](#array__fill). Remplace tous les éléments.  
  
```  
void assign(const Ty& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `val`  
 Valeur à attribuer.  
  
### <a name="remarks"></a>Notes  
 La fonction membre remplace la séquence contrôlée par `*this` par une répétition de `N` éléments ayant la valeur `val`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_assign.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1;   
    c1.assign(4);   
  
// display contents " 4 4 4 4"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 4 4 4  
```  
  
##  <a name="a-namearrayata--arrayat"></a><a name="array__at"></a>  array::at  
 Accède à un élément à une position spécifiée.  
  
```  
reference at(size_type off);

constexpr const_reference at(size_type off) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `off`  
 Position de l'élément auquel accéder.  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent une référence à l'élément de la séquence contrôlée à la position `off`. Si cet emplacement n'est pas valide, la fonction lève un objet de classe `out_of_range`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_at.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display odd elements " 1 3"   
    std::cout << " " << c0.at(1);   
    std::cout << " " << c0.at(3);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
##  <a name="a-namearraybacka--arrayback"></a><a name="array__back"></a>  array::back  
 Accède au dernier élément.  
  
```  
reference back();

constexpr const_reference back() const;
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent une référence au dernier élément de la séquence contrôlée qui ne doit pas être vide.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_back.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    std::cout << " " << c0.back();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="a-namearraybegina--arraybegin"></a><a name="array__begin"></a>  array::begin  
 Désigne le début de la séquence contrôlée.  
  
```  
iterator begin() noexcept;  
const_iterator begin() const noexcept;  
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent un itérateur d'accès aléatoire qui pointe vers le premier élément de la séquence (ou juste après la fin d'une séquence vide).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_begin.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::iterator it2 = c0.begin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearraycbegina--arraycbegin"></a><a name="array__cbegin"></a>  array::cbegin  
 Retourne un itérateur `const` qui traite le premier élément d'une plage.  
  
```  
const_iterator cbegin() const noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d'accès aléatoire `const` qui pointe vers le premier élément de la plage, ou vers l'emplacement situé juste après la fin d'une plage vide (pour une plage vide : `cbegin() == cend()`).  
  
### <a name="remarks"></a>Notes  
 Avec la valeur de retour `cbegin`, les éléments de la plage ne peuvent pas être modifiés.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `begin()` afin de garantir que la valeur de retour est `const_iterator`. En général, elle est utilisée conjointement au mot clé de déduction de type [auto](../cpp/auto-cpp.md), comme le montre l’exemple suivant. Dans cet exemple, il est supposé que `Container` est un conteneur modifiable (non-`const`) de tout type, prenant en charge `begin()` et `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namearraycenda--arraycend"></a><a name="array__cend"></a>  array::cend  
 Retourne un itérateur `const` qui traite l'emplacement situé immédiatement après le dernier élément d'une plage.  
  
```  
const_iterator cend() const noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d'accès aléatoire qui pointe juste après la fin de la plage.  
  
### <a name="remarks"></a>Notes  
 `cend` est utilisé pour vérifier si un itérateur a dépassé la fin de la plage.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `end()` afin de garantir que la valeur de retour est `const_iterator`. En général, elle est utilisée conjointement au mot clé de déduction de type [auto](../cpp/auto-cpp.md), comme le montre l’exemple suivant. Dans cet exemple, il est supposé que `Container` est un conteneur modifiable (autre que `const`) de tout type prenant en charge `end()` et `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 La valeur retournée par `cend` ne doit pas être déréférencée.  
  
##  <a name="a-namearrayconstiteratora--arrayconstiterator"></a><a name="array__const_iterator"></a>  array::const_iterator  
 Type d'un itérateur constant pour la séquence contrôlée.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d’itérateur d’accès aléatoire constant pour la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_const_iterator.cpp  
// compile with: /EHsc /W4  
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> MyArray;   
  
int main()   
{   
    MyArray c0 = {0, 1, 2, 3};   
  
    // display contents " 0 1 2 3"   
    std::cout << "it1:";  
    for ( MyArray::const_iterator it1 = c0.begin();   
          it1 != c0.end();   
          ++it1 ) {  
       std::cout << " " << *it1;   
    }  
    std::cout << std::endl;   
  
    // display first element " 0"   
    MyArray::const_iterator it2 = c0.begin();   
    std::cout << "it2:";  
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
}  
  
```  
  
```Output  
it1: 0 1 2 3                                  
  
it2: 0  
  
```  
  
##  <a name="a-namearrayconstpointera--arrayconstpointer"></a><a name="array__const_pointer"></a>  array::const_pointer  
 Type d'un pointeur constant vers un élément.  
  
```  
typedef const Ty *const_pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir de pointeur constant vers des éléments de la séquence.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_const_pointer.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_pointer ptr = &*c0.begin();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearrayconstreferencea--arrayconstreference"></a><a name="array__const_reference"></a>  array::const_reference  
 Type d'une référence constante à un élément.  
  
```  
typedef const Ty& const_reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir de référence constante à un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_const_reference.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_reference ref = *c0.begin();   
    std::cout << " " << ref;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearrayconstreverseiteratora--arrayconstreverseiterator"></a><a name="array__const_reverse_iterator"></a>  array::const_reverse_iterator  
 Type d'un itérateur inserve constant pour la séquence contrôlée.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d’itérateur inverse constant pour la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_const_reverse_iterator.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::const_reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="a-namearraycrbegina--arraycrbegin"></a><a name="array__crbegin"></a>  array::crbegin  
 Retourne un itérateur const qui traite le premier élément d'un tableau inversé.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur à accès aléatoire inversé const qui traite le premier élément d'un tableau inversé (ou qui traite ce qui était le dernier élément du tableau non inversé).  
  
### <a name="remarks"></a>Notes  
 Avec la valeur de retour `crbegin`, l'objet de tableau ne peut pas être changé.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// array_crbegin.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::iterator v1_Iter;  
   array<int, 2>::const_reverse_iterator v1_rIter;  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of array is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed array is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of array is 1.  
The first element of the reversed array is 2.  
```  
  
##  <a name="a-namearraycrenda--arraycrend"></a><a name="array__crend"></a>  array::crend  
 Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'un tableau inversé.  
  
```  
const_reverse_iterator crend() const noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d'accès aléatoire inversé const qui traite l'emplacement qui suit le dernier élément d'un tableau inversé (emplacement qui précédait le premier élément dans le tableau non inversé).  
  
### <a name="remarks"></a>Notes  
 `crend` est utilisé avec un tableau inversé de la même manière que [array::cend](#array__cend) est utilisé avec un tableau.  
  
 Avec la valeur de retour de `crend` (convenablement décrémentée), l'objet de tableau ne peut pas être modifié.  
  
 `crend` peut être utilisé pour déterminer si un itérateur inversé a atteint la fin de son tableau.  
  
 La valeur retournée par `crend` ne doit pas être déréférencée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// array_crend.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::const_reverse_iterator v1_rIter;  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namearraydataa--arraydata"></a><a name="array__data"></a>  array::data  
 Obtient l'adresse du premier élément.  
  
```  
Ty *data();

const Ty *data() const;
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent l’adresse du premier élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_data.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::pointer ptr = c0.data();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearraydifferencetypea--arraydifferencetype"></a><a name="array__difference_type"></a>  array::difference_type  
 Type d'une distance signée entre deux éléments.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type d'entier signé décrit un objet qui peut représenter la différence entre les adresses de deux éléments quelconques dans la séquence contrôlée. Il est synonyme du type `std::ptrdiff_t`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_difference_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display distance first-last " -4"   
    Myarray::difference_type diff = c0.begin() - c0.end();   
    std::cout << " " << diff;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
-4  
```  
  
##  <a name="a-namearrayemptya--arrayempty"></a><a name="array__empty"></a>  array::empty  
 Vérifie l'absence d'éléments.  
  
```  
constexpr bool empty() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne true uniquement si `N == 0`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_empty.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display whether c0 is empty " false"   
    std::cout << std::boolalpha << " " << c0.empty();   
    std::cout << std::endl;   
  
    std::array<int, 0> c1;   
  
// display whether c1 is empty " true"   
    std::cout << std::boolalpha << " " << c1.empty();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
false  
true  
```  
  
##  <a name="a-namearrayenda--arrayend"></a><a name="array__end"></a>  array::end  
 Désigne la fin de la séquence contrôlée.  
  
```  
reference end();

const_reference end() const;
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent un itérateur d'accès aléatoire qui pointe juste après la fin de la séquence.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_end.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::iterator it2 = c0.end();   
    std::cout << " " << *--it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="a-namearrayfilla--arrayfill"></a><a name="array__fill"></a>  array::fill  
 Efface un tableau et copie les éléments spécifiés dans le tableau vide.  
  
```  
void fill(const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|Valeur de l'élément inséré dans le tableau.|  
  
### <a name="remarks"></a>Notes  
 `fill` remplace chaque élément du tableau par la valeur spécifiée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// array_fill.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::iterator iter;  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v1.fill(3);  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namearrayfronta--arrayfront"></a><a name="array__front"></a>  array::front  
 Accède au premier élément.  
  
```  
reference front();

constexpr const_reference front() const;
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent une référence au premier élément de la séquence contrôlée qui ne doit pas être vide.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_front.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    std::cout << " " << c0.front();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearrayiteratora--arrayiterator"></a><a name="array__iterator"></a>  array::iterator  
 Type d'un itérateur pour la séquence contrôlée.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d'itérateur à accès aléatoire pour la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_iterator.cpp   
// compile with: /EHsc /W4  
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> MyArray;   
  
int main()   
{   
    MyArray c0 = {0, 1, 2, 3};   
  
    // display contents " 0 1 2 3"   
    std::cout << "it1:";  
    for ( MyArray::iterator it1 = c0.begin();   
          it1 != c0.end();   
          ++it1 ) {  
       std::cout << " " << *it1;   
    }  
    std::cout << std::endl;   
  
    // display first element " 0"   
    MyArray::iterator it2 = c0.begin();   
    std::cout << "it2:";  
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
}  
  
```  
  
```Output  
it1: 0 1 2 3                                  
  
it2: 0  
  
```  
  
##  <a name="a-namearraymaxsizea--arraymaxsize"></a><a name="array__max_size"></a>  array::max_size  
 Compte le nombre d'éléments.  
  
```  
constexpr size_type max_size() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `N`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_max_size.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display (maximum) size " 4"   
    std::cout << " " << c0.max_size();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="a-namearrayoperatorata--arrayoperator"></a><a name="array__operator_at"></a>  array::operator[]  
 Accède à un élément à une position spécifiée.  
  
```  
reference operator[](size_type off);

constexpr const_reference operator[](size_type off) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `off`  
 Position de l'élément auquel accéder.  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent une référence à l'élément de la séquence contrôlée à la position `off`. Si cette position n'est pas valide, le comportement est indéfini.  
  
Il existe également une fonction non-membre [get](array-functions.md#get_function) disponible pour obtenir une référence à un élément d’un `array`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_operator_sub.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display odd elements " 1 3"   
    std::cout << " " << c0[1];   
    std::cout << " " << c0[3];   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
1 3  
```  
  
##  <a name="a-namearrayoperatoreqa--arrayoperator"></a><a name="array__operator_eq"></a>  array::operator=  
 Remplace la séquence contrôlée.  
  
```  
array <Value>%  operator=(array <Value>% right);
```  
  
### <a name="parameters"></a>Paramètres  
 droite  
 Conteneur à copier.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre attribue chaque élément de `right` à l’élément correspondant de la séquence contrôlée, puis retourne `*this`. Vous l’utilisez pour remplacer la séquence contrôlée par une copie de la séquence contrôlée dans `right`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_operator_as.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1;   
    c1 = c0;   
  
// display copied contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
##  <a name="a-namearraypointera--arraypointer"></a><a name="array__pointer"></a>  array::pointer  
 Type d'un pointeur vers un élément.  
  
```  
typedef Ty *pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir de pointeur vers des éléments de la séquence.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_pointer.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::pointer ptr = &*c0.begin();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearrayrbegina--arrayrbegin"></a><a name="array__rbegin"></a>  array::rbegin  
 Désigne le début de la séquence contrôlée inverse.  
  
```  
reverse_iterator rbegin()noexcept;  
const_reverse_iterator rbegin() const noexcept;  
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent un itérateur inverse qui pointe juste après la fin de la séquence contrôlée. Par conséquent, il désigne le début de la séquence inverse.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_rbegin.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::const_reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="a-namearrayreferencea--arrayreference"></a><a name="array__reference"></a>  array::reference  
 Type d'une référence à un élément.  
  
```  
typedef Ty& reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet qui peut servir de référence à un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_reference.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::reference ref = *c0.begin();   
    std::cout << " " << ref;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearrayrenda--arrayrend"></a><a name="array__rend"></a>  array::rend  
 Désigne la fin de la séquence contrôlée inverse.  
  
```  
reverse_iterator rend()noexcept;  
const_reverse_iterator rend() const noexcept;  
```  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent un itérateur inverse qui pointe vers le premier élément de la séquence (ou juste après la fin d'une séquence vide). Par conséquent, il désigne la fin de la séquence inverse.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_rend.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_reverse_iterator it2 = c0.rend();   
    std::cout << " " << *--it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="a-namearrayreverseiteratora--arrayreverseiterator"></a><a name="array__reverse_iterator"></a>  array::reverse_iterator  
 Type d'un itérateur inverse pour la séquence contrôlée.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d’itérateur inverse pour la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_reverse_iterator.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="a-namearraysizea--arraysize"></a><a name="array__size"></a>  array::size  
 Compte le nombre d'éléments.  
  
```  
constexpr size_type size() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `N`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_size.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display size " 4"   
    std::cout << " " << c0.size();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="a-namearraysizetypea--arraysizetype"></a><a name="array__size_type"></a>  array::size_type  
 Type d’une distance non signée entre deux éléments.  
  
```  
typedef std::size_t size_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type d'entier non signé décrit un objet qui peut représenter la longueur de n'importe quelle séquence contrôlée. Il est synonyme du type `std::size_t`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_size_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display distance last-first " 4"   
    Myarray::size_type diff = c0.end() - c0.begin();   
    std::cout << " " << diff;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="a-namearrayswapa--arrayswap"></a><a name="array__swap"></a>  array::swap  
Échange le contenu de ce tableau avec un autre tableau.  
  
```  
void swap(array& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Tableau avec lequel échanger le contenu.  
  
### <a name="remarks"></a>Notes  
La fonction membre échange les séquences contrôlées entre `*this` et `right`. Il effectue un nombre d’assignations d’élément et d’appels de constructeur proportionnel à `N`.  

Il existe également une fonction non-membre [swap](array-functions.md#swap_function) disponible pour échanger deux instances d’`array`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_swap.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
    c0.swap(c1);   
  
// display swapped contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    swap(c0, c1);   
  
// display swapped contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
0 1 2 3  
```  
  
##  <a name="a-namearrayvaluetypea--arrayvaluetype"></a><a name="array__value_type"></a>  array::value_type  
 Type d’un élément.  
  
```  
typedef Ty value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Ty`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__array__array_value_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        {   
        Myarray::value_type val = *it;   
        std::cout << " " << val;   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<array>](../standard-library/array.md)


