---
title: "&lt;vector&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 14308c0789851af423fd687f88acfe9177d89aff
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  operator!=  
 Teste si l’objet situé à gauche de l’opérateur n’est pas égal à l’objet situé à droite.  
  
```  
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **vector**.  
  
 `right`  
 Objet de type **vector**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les vecteurs ne sont pas égaux ; **false** si les vecteurs sont égaux.  
  
### <a name="remarks"></a>Notes  
 Deux vecteurs sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// vector_op_ne.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
     v2.push_back( 2 );  
  
   if ( v1 != v2 )  
      cout << "Vectors not equal." << endl;  
   else  
      cout << "Vectors equal." << endl;  
}  
```  
  
```Output  
Vectors not equal.  
```  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 Teste si l’objet situé à gauche de l’opérateur est inférieur à l’objet situé à droite.  
  
```  
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **vector**.  
  
 `right`  
 Objet de type **vector**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le vecteur situé à gauche de l’opérateur est strictement inférieur au vecteur situé à droite de l’opérateur ; sinon, **false**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// vector_op_lt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 < v2 )  
      cout << "Vector v1 is less than vector v2." << endl;  
   else  
      cout << "Vector v1 is not less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than vector v2.  
```  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 Teste si l’objet situé à gauche de l’opérateur est inférieur ou égal à l’objet situé à droite.  
  
```  
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **vector**.  
  
 `right`  
 Objet de type **vector**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le vecteur situé à gauche de l’opérateur est inférieur ou égal au vecteur situé à droite de l’opérateur ; sinon, **false**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// vector_op_le.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 <= v2 )  
      cout << "Vector v1 is less than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than or equal to vector v2.  
```  
  
##  <a name="operator_eq_eq"></a>  operator==  
 Teste si l’objet situé à gauche de l’opérateur est égal à l’objet situé à droite.  
  
```  
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **vector**.  
  
 `right`  
 Objet de type **vector**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le vecteur situé à gauche de l’opérateur est égal au vecteur situé à droite de l’opérateur ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Deux vecteurs sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// vector_op_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v2.push_back( 1 );  
  
   if ( v1 == v2 )  
      cout << "Vectors equal." << endl;  
   else  
      cout << "Vectors not equal." << endl;  
}  
```  
  
```Output  
Vectors equal.  
```  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 Teste si l’objet situé à gauche de l’opérateur est supérieur à l’objet situé à droite.  
  
```  
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **vector**.  
  
 `right`  
 Objet de type **vector**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le vecteur situé à gauche de l’opérateur est supérieur au vecteur situé à droite de l’opérateur ; sinon, **false**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// vector_op_gt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
   v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 > v2 )  
      cout << "Vector v1 is greater than vector v2." << endl;  
   else  
      cout << "Vector v1 is not greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than vector v2.  
```  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 Teste si l’objet situé à gauche de l’opérateur est supérieur ou égal à l’objet situé à droite.  
  
```  
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type **vector**.  
  
 `right`  
 Objet de type **vector**.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le vecteur situé à gauche de l’opérateur est supérieur ou égal au vecteur situé à droite de l’opérateur ; sinon, **false**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// vector_op_ge.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
     v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 >= v2 )  
      cout << "Vector v1 is greater than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than or equal to vector v2.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<vector>](../standard-library/vector.md)


