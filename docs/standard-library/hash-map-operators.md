---
title: "&lt;hash_map&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 13
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 7d47da5bcdb614e5eaf43fbabbe836226e3f907b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt;, opérateurs
|||  
|-|-|  
|[operator!=](#op_neq)|[operator!=](#op_neq)|
  
##  <a name="op_neq"></a>  operator!=  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_map, classe](../standard-library/unordered-map-class.md).  
  
 Vérifie si l’objet hash_map situé à gauche de l’opérateur n’est pas égal à l’objet hash_map situé à droite.  
  
```  
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `hash_map`.  
  
 `right`  
 Objet de type `hash_map`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les hash_maps ne sont pas égaux ; **false** si les hash_maps sont égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets hash_map est basée sur une comparaison par paire de leurs éléments. Deux hash_map sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
 Membres de la [< hash_map >](../standard-library/hash-map.md) et [< hash_set >](../standard-library/hash-set.md) fichiers d’en-tête dans le [ stdext Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// hash_map_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="op_eq_eq"></a>  operator== 
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_map, classe](../standard-library/unordered-map-class.md).  
  
 Vérifie si l’objet hash_map situé à gauche de l’opérateur est égal à l’objet hash_map situé à droite.  
  
```  
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `hash_map`.  
  
 `right`  
 Objet de type `hash_map`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le hash_map situé à gauche de l’opérateur est égal au hash_map situé à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets hash_map est basée sur une comparaison par paire de leurs éléments. Deux hash_map sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
    
### <a name="example"></a>Exemple  
  
```cpp  
// hash_map_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="op_neq"></a>  operator!=  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_multimap, classe](../standard-library/unordered-multimap-class.md).  
  
 Vérifie si l’objet hash_multimap situé à gauche de l’opérateur n’est pas égal à l’objet hash_multimap situé à droite.  
  
```  
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `hash_multimap`.  
  
 `right`  
 Objet de type `hash_multimap`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les hash_multimaps ne sont pas égaux ; **false** si les hash_multimaps sont égaux.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets hash_multimap est basée sur une comparaison par paire de leurs éléments. Deux hash_multimaps sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
   
### <a name="example"></a>Exemple  
  
```cpp  
// hash_multimap_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
##  <a name="op_eq_eq"></a>  operator==  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_multimap, classe](../standard-library/unordered-multimap-class.md).  
  
 Vérifie si l’objet hash_multimap situé à gauche de l’opérateur est égal à l’objet hash_multimap situé à droite.  
  
```  
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Objet de type `hash_multimap`.  
  
 `right`  
 Objet de type `hash_multimap`.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le hash_multimap situé à gauche de l’opérateur est égal au hash_multimap situé à droite de l’opérateur. Sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 La comparaison entre les objets hash_multimap est basée sur une comparaison par paire de leurs éléments. Deux hash_multimaps sont égaux s’ils ont le même nombre d’éléments et si leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// hash_multimap_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair<int, int> Int_Pair;  
  
   for (i = 0; i < 3; i++)  
   {  
      hm1.insert(Int_Pair(i, i));  
      hm2.insert(Int_Pair(i, i*i));  
      hm3.insert(Int_Pair(i, i));  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [<hash_map>](../standard-library/hash-map.md)


