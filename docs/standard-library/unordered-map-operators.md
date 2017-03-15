---
title: "&lt;unordered_map&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: c78d1dda2a61a85bde238167b75eace09af598b6
ms.lasthandoff: 02/24/2017

---
# <a name="ltunorderedmapgt-operators"></a>&lt;unordered_map&gt;, opérateurs
|||||  
|-|-|-|-|  
|[operator!=](#operator_neq)|[operator==](#operator_eq_eq)|[operator!=](#operator_neq_multimap)|[operator==](#operator_eq_eq_multimap)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Teste si l’objet [unordered_map](../standard-library/unordered-map-class.md) situé à gauche de l’opérateur n’est pas égal à l’objet unordered_map situé à droite.  
  
```
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `unordered_map`.  
  
 `right`  
 Objet de type `unordered_map`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les objets unordered_map ne sont pas égaux ; `false` s’ils sont égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets unordered_map n’est pas affectée par l’ordre arbitraire dans lequel ils stockent leurs éléments. Deux objets unordered_map sont égaux s’ils ont le même nombre d’éléments et que les éléments d’un conteneur constituent une permutation des éléments de l’autre conteneur. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// unordered_map_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Sortie :**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Teste si l’objet [unordered_map](../standard-library/unordered-map-class.md) situé à gauche de l’opérateur est égal à l’objet unordered_map situé à droite.  
  
```
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `unordered_map`.  
  
 `right`  
 Objet de type `unordered_map`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les objets unordered_map sont égaux ; `false` s’ils ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets unordered_map n’est pas affectée par l’ordre arbitraire dans lequel ils stockent leurs éléments. Deux objets unordered_map sont égaux s’ils ont le même nombre d’éléments et que les éléments d’un conteneur constituent une permutation des éléments de l’autre conteneur. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// unordered_map_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Sortie :**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
##  <a name="a-nameoperatorneqmultimapa--operator"></a><a name="operator_neq_multimap"></a>  operator!=  
 Teste si l’objet [unordered_multimap](../standard-library/unordered-multimap-class.md) situé à gauche de l’opérateur n’est pas égal à l’objet unordered_multimap situé à droite.  
  
```
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `unordered_multimap`.  
  
 `right`  
 Objet de type `unordered_multimap`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les objets unordered_multimap ne sont pas égaux ; `false` s’ils sont égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets unordered_multimap n’est pas affectée par l’ordre arbitraire dans lequel ils stockent leurs éléments. Deux objets unordered_multimap sont égaux s’ils ont le même nombre d’éléments et que les éléments d’un conteneur constituent une permutation des éléments de l’autre conteneur. Sinon, il ne sont pas égaux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// unordered_multimap_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Sortie :**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="a-nameoperatoreqeqmultimapa--operator"></a><a name="operator_eq_eq_multimap"></a>  operator==  
 Teste si l’objet [unordered_multimap](../standard-library/unordered-multimap-class.md) situé à gauche de l’opérateur est égal à l’objet unordered_multimap situé à droite.  
  
```
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `unordered_multimap`.  
  
 `right`  
 Objet de type `unordered_multimap`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les objets unordered_multimap sont égaux ; `false` s’ils ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets unordered_multimap n’est pas affectée par l’ordre arbitraire dans lequel ils stockent leurs éléments. Deux objets unordered_multimap sont égaux s’ils ont le même nombre d’éléments et que les éléments d’un conteneur constituent une permutation des éléments de l’autre conteneur. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// unordered_multimap_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd  
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Sortie :**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
## <a name="see-also"></a>Voir aussi  
 [<unordered_map>](../standard-library/unordered-map.md)




