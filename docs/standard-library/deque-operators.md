---
title: "&lt;deque&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 482d7c92-54c7-493b-99e6-2a73617481a5
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 18fafc735fe05dbba24058394bbcd7fefd45cffd
ms.lasthandoff: 02/24/2017

---
# <a name="ltdequegt-operators"></a>&lt;deque&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Teste si l'objet deque situé à gauche de l'opérateur n'est pas égal à l'objet deque situé à droite.  
  
```
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `deque`.  
  
 `right`  
 Objet de type `deque`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets de file d’attente à deux extrémités ne sont pas égaux ; **false** s’ils sont égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets de file d’attente à deux extrémités est basée sur une comparaison par paire de leurs éléments. Deux file d’attente à deux extrémités sont égales si elles ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// deque_op_ne.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c2.push_back( 2 );  
  
   if ( c1 != c2 )  
      cout << "The deques are not equal." << endl;  
   else  
      cout << "The deques are equal." << endl;  
}  
\* Output:   
The deques are not equal.  
*\  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 Teste si l'objet deque situé à gauche de l'opérateur est inférieur à l'objet deque situé à droite.  
  
```
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `deque`.  
  
 `right`  
 Objet de type `deque`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la file d’attente à deux extrémités à gauche de l’opérateur est inférieure et non égale à la file d’attente à deux extrémités à droite de l’opérateur ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets de file d’attente à deux extrémités est basée sur une comparaison par paire de leurs éléments. La relation d'infériorité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// deque_op_lt.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 < c2 )  
      cout << "Deque c1 is less than deque c2." << endl;  
   else  
      cout << "Deque c1 is not less than deque c2." << endl;  
}  
\* Output:   
Deque c1 is less than deque c2.  
*\   
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 Teste si l'objet deque situé à gauche de l'opérateur est inférieur ou égal à l'objet deque situé à droite.  
  
```
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `deque`.  
  
 `right`  
 Objet de type `deque`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la file d’attente à deux extrémités à gauche de l’opérateur est inférieure ou égale à la file d’attente à deux extrémités à droite de l’opérateur ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets de file d’attente à deux extrémités est basée sur une comparaison par paire de leurs éléments. La relation d'infériorité ou d'égalité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// deque_op_le.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 <= c2 )  
      cout << "Deque c1 is less than or equal to deque c2." << endl;  
   else  
      cout << "Deque c1 is greater than deque c2." << endl;  
}  
\* Output:   
Deque c1 is less than or equal to deque c2.  
*\  
  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Teste si l'objet deque situé à gauche de l'opérateur est égal à l'objet deque situé à droite.  
  
```
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `deque`.  
  
 `right`  
 Objet de type `deque`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la file d’attente à deux extrémités à gauche de l’opérateur est égale à la file d’attente à deux extrémités à droite de l’opérateur ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets de file d’attente à deux extrémités est basée sur une comparaison par paire de leurs éléments. Deux file d’attente à deux extrémités sont égales si elles ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// deque_op_eq.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c2.push_back( 1 );  
  
   if ( c1 == c2 )  
      cout << "The deques are equal." << endl;  
   else  
      cout << "The deques are not equal." << endl;  
  
   c1.push_back( 1 );  
   if ( c1 == c2 )  
      cout << "The deques are equal." << endl;  
   else  
      cout << "The deques are not equal." << endl;  
}  
\* Output:   
The deques are equal.  
The deques are not equal.  
*\  
  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 Teste si l'objet deque situé à gauche de l'opérateur est supérieur à l'objet deque situé à droite.  
  
```
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `deque`.  
  
 `right`  
 Objet de type `deque`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la file d’attente à deux extrémités à gauche de l’opérateur est supérieure à la file d’attente à deux extrémités à droite de l’opérateur ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets de file d’attente à deux extrémités est basée sur une comparaison par paire de leurs éléments. La relation de supériorité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// deque_op_gt.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 > c2 )  
      cout << "Deque c1 is greater than deque c2." << endl;  
   else  
      cout << "Deque c1 is not greater than deque c2." << endl;  
}  
\* Output:   
Deque c1 is greater than deque c2.  
*\  
  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 Teste si l'objet deque situé à gauche de l'opérateur est supérieur ou égal à l'objet deque situé à droite.  
  
```
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `deque`.  
  
 `right`  
 Objet de type `deque`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la file d’attente à deux extrémités à gauche de l’opérateur est supérieure ou égale à la file d’attente à deux extrémités à droite de l’opérateur ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets de file d’attente à deux extrémités est basée sur une comparaison par paire de leurs éléments. La relation de supériorité ou d'égalité entre deux objets est basée sur une comparaison de la première paire d'éléments inégaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// deque_op_ge.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 >= c2 )  
      cout << "Deque c1 is greater than or equal to deque c2." << endl;  
   else  
      cout << "Deque c1 is less than deque c2." << endl;  
}  
\* Output:   
Deque c1 is greater than or equal to deque c2.  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<deque>](../standard-library/deque.md)



