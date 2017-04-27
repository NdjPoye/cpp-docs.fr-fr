---
title: "&lt;liste&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 617ac2187ec3cd6d46cec6076fa72cc437803714
ms.lasthandoff: 02/24/2017

---
# <a name="ltlistgt-operators"></a>&lt;list&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  operator!=  
 Teste si l'objet de liste situé à gauche de l'opérateur n'est pas égal à l'objet de liste situé à droite.  
  
```
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **list**.  
  
 `right`  
 Objet de type **list**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les listes ne sont pas égales ; **false** si les listes sont égales.  
  
### <a name="remarks"></a>Remarques  
 La comparaison entre les objets de liste est basée sur une comparaison par paire de leurs éléments. Deux listes sont égales si elles ont le même nombre d'éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_op_ne.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
list <int> c1, c2;  
c1.push_back( 1 );  
c2.push_back( 2 );  
  
if ( c1 != c2 )  
cout << "Lists not equal." << endl;  
else  
cout << "Lists equal." << endl;  
}  
\* Output:  
Lists not equal.  
*\  
```  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 Teste si l'objet de liste situé à gauche de l'opérateur est inférieur à l'objet de liste situé à droite.  
  
```
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **list**.  
  
 `right`  
 Objet de type **list**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la liste située à gauche de l’opérateur est inférieure mais pas égale à la liste située à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Remarques  
 La comparaison entre les objets de liste est basée sur une comparaison par paire de leurs éléments. La relation d'infériorité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_op_lt.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 < c2 )  
      cout << "List c1 is less than list c2." << endl;  
   else  
      cout << "List c1 is not less than list c2." << endl;  
}  
\* Output:   
List c1 is less than list c2.  
*\   
```  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 Teste si l'objet de liste situé à gauche de l'opérateur est inférieur ou égal à l'objet de liste situé à droite.  
  
```
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **list**.  
  
 `right`  
 Objet de type **list**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la liste située à gauche de l’opérateur est inférieure ou égale à la liste située à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Remarques  
 La comparaison entre les objets de liste est basée sur une comparaison par paire de leurs éléments. La relation d'infériorité ou d'égalité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_op_le.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 <= c2 )  
      cout << "List c1 is less than or equal to list c2." << endl;  
   else  
      cout << "List c1 is greater than list c2." << endl;  
}  
\* Output:   
List c1 is less than or equal to list c2.  
*\  
```  
  
##  <a name="operator_eq_eq"></a>  operator==  
 Teste si l'objet de liste situé à gauche de l'opérateur est égal à l'objet de liste situé à droite.  
  
```
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **list**.  
  
 `right`  
 Objet de type **list**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la liste située à gauche de l’opérateur est égale à la liste située à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Remarques  
 La comparaison entre les objets de liste est basée sur une comparaison par paire de leurs éléments. Deux listes sont égales si elles ont le même nombre d'éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_op_eq.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
int main( )   
{  
   using namespace std;   
  
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c2.push_back( 1 );  
  
   if ( c1 == c2 )  
      cout << "The lists are equal." << endl;  
   else  
      cout << "The lists are not equal." << endl;  
}  
\* Output:   
The lists are equal.  
*\  
```  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 Teste si l'objet de liste situé à gauche de l'opérateur est supérieur à l'objet de liste situé à droite.  
  
```
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **list**.  
  
 `right`  
 Objet de type **list**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la liste située à gauche de l’opérateur est supérieure à la liste située à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Remarques  
 La comparaison entre les objets de liste est basée sur une comparaison par paire de leurs éléments. La relation de supériorité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_op_gt.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 > c2 )  
      cout << "List c1 is greater than list c2." << endl;  
   else  
      cout << "List c1 is not greater than list c2." << endl;  
}  
\* Output:   
List c1 is greater than list c2.  
*\  
```  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 Teste si l'objet de liste situé à gauche de l'opérateur est supérieur ou égal à l'objet de liste situé à droite.  
  
```
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **list**.  
  
 `right`  
 Objet de type **list**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la liste située à gauche de l’opérateur est supérieure ou égale à la liste située à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Remarques  
 La comparaison entre les objets de liste est basée sur une comparaison par paire de leurs éléments. La relation de supériorité ou d'égalité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_op_ge.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 >= c2 )  
      cout << "List c1 is greater than or equal to list c2." << endl;  
   else  
      cout << "List c1 is less than list c2." << endl;  
}  
\* Output:   
List c1 is greater than or equal to list c2.  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<list>](../standard-library/list.md)




