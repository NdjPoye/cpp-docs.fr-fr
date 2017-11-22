---
title: "&lt;memory&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
dev_langs:
- C++
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 95563f5eeb70d33e3ebba4de0aead276a2230669
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltmemorygt-operators"></a>&lt;memory&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|  
|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 Teste l'inégalité entre des objets.  
  
```  
template <class Type, class Other>  
bool operator!=(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>  
bool operator!=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator!=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 L'un des objets dont l'inégalité doit être testée.  
  
 `right`  
 L'un des objets dont l'inégalité doit être testée.  
  
 `Ty1`  
 Type contrôlé par le pointeur partagé de gauche.  
  
 `Ty2`  
 Type contrôlé par le pointeur partagé de droite.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets ne sont pas égaux, **false** si les objets sont égaux.  
  
### <a name="remarks"></a>Remarques  
 Le premier opérateur de modèle retourne false. (Tous les allocateurs par défaut sont égaux).  
  
 Les deuxième et troisième opérateurs de modèle retournent `!(left == right)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// memory_op_me.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <char>:: allocator_type v1Alloc;  
  
   if ( Alloc != v1Alloc )  
      cout << "The allocator objects Alloc & v1Alloc not are equal."  
           << endl;  
   else  
      cout << "The allocator objects Alloc & v1Alloc are equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects Alloc & v1Alloc are equal.  
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__memory__operator_ne.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 != sp0 == " << std::boolalpha   
        << (sp0 != sp0) << std::endl;   
    std::cout << "sp0 != sp1 == " << std::boolalpha   
        << (sp0 != sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 != sp0 == false  
sp0 != sp1 == true  
```  
  
##  <a name="op_eq_eq"></a>  operator==  
 Teste l'égalité entre des objets.  
  
```  
template <class Type, class Other>  
bool operator==(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator==(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>  
bool operator==(
    const shared_ptr<Ty1>& left;,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 L'un des objets dont l'égalité doit être testée.  
  
 `right`  
 L'un des objets dont l'égalité doit être testée.  
  
 `Ty1`  
 Type contrôlé par le pointeur partagé de gauche.  
  
 `Ty2`  
 Type contrôlé par le pointeur partagé de droite.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les objets sont égaux, `false` si les objets ne sont pas égaux.  
  
### <a name="remarks"></a>Remarques  
 Le premier opérateur de modèle retourne true. (Tous les allocateurs par défaut sont égaux).  
  
 Les deuxième et troisième opérateurs de modèle retournent ` left.get() ==  right.get()`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// memory_op_eq.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<char> Alloc;  
   vector <int>:: allocator_type v1Alloc;  
  
   allocator<char> cAlloc(Alloc);   
   allocator<int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__memory__operator_eq.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 == sp0 == " << std::boolalpha   
        << (sp0 == sp0) << std::endl;   
    std::cout << "sp0 == sp1 == " << std::boolalpha   
        << (sp0 == sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == sp0 == true  
sp0 == sp1 == false  
```  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
 Teste si un objet est supérieur ou égal à un second objet.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator>=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>  
bool operator>=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 L'un des objets à comparer.  
  
 `right`  
 L'un des objets à comparer.  
  
 `Ty1`  
 Type contrôlé par le pointeur partagé de gauche.  
  
 `Ty2`  
 Type contrôlé par le pointeur partagé de droite.  
  
### <a name="remarks"></a>Remarques  
 Les opérateurs de modèle retournent `left.get() >= right.get()`.  
  
##  <a name="op_lt"></a>  operator&lt;  
 Teste si un objet est inférieur à un second objet.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 L'un des objets à comparer.  
  
 `right`  
 L'un des objets à comparer.  
  
 `Ty1`  
 Type contrôlé par le pointeur de gauche.  
  
 `Ty2`  
 Type contrôlé par le pointeur de droite.  
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
 Teste si un objet est inférieur ou égal à un second objet.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 L'un des objets à comparer.  
  
 `right`  
 L'un des objets à comparer.  
  
 `Ty1`  
 Type contrôlé par le pointeur partagé de gauche.  
  
 `Ty2`  
 Type contrôlé par le pointeur partagé de droite.  
  
### <a name="remarks"></a>Remarques  
 Les opérateurs de modèle de retour`left.get() <= right.get()`  
  
##  <a name="op_gt"></a>  operator&gt;  
 Teste si un objet est supérieur à un second objet.  
  
```  
template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator>(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>  
bool operator>(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 L'un des objets à comparer.  
  
 `right`  
 L'un des objets à comparer.  
  
 `Ty1`  
 Type contrôlé par le pointeur partagé de gauche.  
  
 `Ty2`  
 Type contrôlé par le pointeur partagé de droite.  
  
##  <a name="op_lt_lt"></a>  operator&lt;&lt;  
Écrit le pointeur partagé dans le flux.  
  
```  
template <class Elem, class Tr, class Ty>  
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,  
    shared_ptr<Ty>& sp);
```  
  
### <a name="parameters"></a>Paramètres  
 `Elem`  
 Type de l’élément de flux.  
  
 `Tr`  
 Type de caractéristiques d’élément de flux.  
  
 `Ty`  
 Type contrôlé par le pointeur partagé.  
  
 `out`  
 Flux de sortie.  
  
 `sp`  
 Pointeur partagé.  
  
### <a name="remarks"></a>Remarques  
 La fonction de modèle retourne `out << sp.get()`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__memory__operator_sl.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(5));   
  
    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == 3f3040 (varies)  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<memory>](../standard-library/memory.md)

