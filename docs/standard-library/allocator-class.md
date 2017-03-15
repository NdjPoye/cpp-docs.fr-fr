---
title: allocator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::allocator
- allocator
- memory/std::allocator
- std.allocator
dev_langs:
- C++
helpviewer_keywords:
- allocator class
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 4c9e2c1acffd7286644ca61a4ef782e7b3a11eef
ms.lasthandoff: 02/24/2017

---
# <a name="allocator-class"></a>allocator, classe
Cette classe de modèle décrit un objet qui gère l’allocation et la libération de stockage pour des tableaux d’objets de type **Type**. Un objet de classe **allocator** est l’objet allocateur par défaut spécifié dans les constructeurs pour plusieurs classes de modèle de conteneur dans la bibliothèque C++ Standard.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type>  
class allocator  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type*  
 Type d'objet pour lequel le stockage est alloué ou libéré.  
  
## <a name="remarks"></a>Notes  
 Tous les conteneurs de bibliothèque C++ Standard ont un paramètre de modèle qui est **allocator** par défaut. La construction d'un conteneur avec un allocateur personnalisé permet de contrôler l'allocation et la libération des éléments de ce conteneur.  
  
 Par exemple, un objet allocateur peut allouer du stockage sur un segment de mémoire privé ou dans la mémoire partagée, ou il peut optimiser la mémoire pour les objets de petite ou de grande taille. Il peut également spécifier, via les définitions de types qu’il fournit, que les éléments soient accessibles via des objets d’accesseur spéciaux qui gèrent la mémoire partagée, ou effectuer un nettoyage de la mémoire automatique. Ainsi, une classe qui alloue du stockage à l’aide d’un objet allocateur doit utiliser ces types pour déclarer des objets pointeur et référence, comme le font les conteneurs dans la bibliothèque C++ Standard.  
  
 **(C_++98/03 uniquement)**Quand vous dérivez de la classe allocator, vous devez fournir un struct [rebind](#allocator__rebind), dont le typedef `_Other` référence votre classe nouvellement dérivée.  
  
 Ainsi, un allocateur définit les types suivants :  
  
- [pointer](#allocator__pointer) se comporte comme un pointeur vers **Type**.  
  
- [const_pointer](#allocator__const_pointer) se comporte comme un pointeur const vers **Type**.  
  
- [reference](#allocator__reference) se comporte comme une référence à **Type**.  
  
- [const_reference](#allocator__const_reference) se comporte comme une référence const à **Type**.  
  
 Ces **Type**s spécifient la forme que les pointeurs et les références doivent prendre pour les éléments alloués. ([allocator::pointer](#allocator__pointer) n’est pas nécessairement identique à **Type**\* pour tous les objets allocateur, même s’il a cette définition évidente pour la classe **allocator**.)  
  
 **C++11 et versions ultérieures :** Pour autoriser les opérations de déplacement dans votre allocateur, utilisez l’interface d’allocateur minimale et implémentez le constructeur de copie, les opérateurs == et !=, allocate et deallocate. Pour plus d’informations et pour obtenir un exemple, consultez [Allocateurs](../standard-library/allocators.md)  
  
## <a name="members"></a>Membres  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[allocator](#allocator__allocator)|Constructeurs utilisés pour créer des objets `allocator`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[const_pointer](#allocator__const_pointer)|Type qui fournit un pointeur constant vers le type d'objet géré par l'allocateur.|  
|[const_reference](#allocator__const_reference)|Type qui fournit une référence constante au type d'objet géré par l'allocateur.|  
|[difference_type](#allocator__difference_type)|Type intégral signé qui peut représenter la différence entre des valeurs de pointeurs vers le type d'objet géré par l'allocateur.|  
|[pointer](#allocator__pointer)|Type qui fournit un pointeur vers le type d'objet géré par l'allocateur.|  
|[reference](#allocator__reference)|Type qui fournit une référence au type d'objet géré par l'allocateur.|  
|[size_type](#allocator__size_type)|Type intégral non signé qui peut représenter la longueur d'une séquence qu'un objet de classe de modèle `allocator` peut allouer.|  
|[value_type](#allocator__value_type)|Type géré par l'allocateur.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[address](#allocator__address)|Recherche l'adresse d'un objet dont la valeur est spécifiée.|  
|[allocate](#allocator__allocate)|Alloue un bloc de mémoire suffisamment grand pour stocker au moins un nombre spécifié d'éléments.|  
|[construct](#allocator__construct)|Construit un type d'objet spécifique à une adresse spécifiée qui est initialisée avec une valeur spécifiée.|  
|[deallocate](#allocator__deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[destroy](#allocator__destroy)|Appelle un destructeur d'objets sans libérer la mémoire où l'objet était stocké.|  
|[max_size](#allocator__max_size)|Retourne le nombre d'éléments de type `Type` qui pourraient être alloués par un objet de classe `allocator` avant que la mémoire libre soit complètement utilisée.|  
|[rebind](#allocator__rebind)|Structure qui permet à un allocateur d'objets d'un type d'allouer du stockage pour les objets d'un autre type.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator=](#allocator__operator_eq)|Assigne un objet `allocator` à un autre objet `allocator`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<memory>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameallocatoraddressa--allocatoraddress"></a><a name="allocator__address"></a>  allocator::address  
 Recherche l'adresse d'un objet dont la valeur est spécifiée.  
  
```  
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` val`  
 Valeur const ou nonconst de l’objet dont l’adresse est recherchée.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur const ou nonconst vers l’objet trouvé d’une valeur const ou nonconst, respectivement.  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent l’adresse de ` val`, sous la forme que les pointeurs doivent prendre pour les éléments alloués.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_address.cpp  
// compile with: /EHsc  
#include <memory>  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 8;  
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );  
   // v1Ptr = v1Alloc.address( k );  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.  
```  
  
##  <a name="a-nameallocatorallocatea--allocatorallocate"></a><a name="allocator__allocate"></a>  allocator::allocate  
 Alloue un bloc de mémoire suffisamment grand pour stocker au moins un nombre spécifié d'éléments.  
  
```  
pointer allocate(size_type count, const void* _Hint);
```  
  
### <a name="parameters"></a>Paramètres  
 ` count`  
 Nombre d’éléments pour lesquels un stockage suffisant doit être alloué.  
  
 *_Hint*  
 Pointeur const pouvant aider l’objet allocateur à satisfaire la demande de stockage en recherchant l’adresse d’un objet alloué avant la demande.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet alloué ou null si la mémoire n’a pas été allouée.  
  
### <a name="remarks"></a>Notes  
 La fonction membre alloue du stockage à un tableau d’éléments count de type **Type**, en appelant l’opérateur new(` count`). Retourne un pointeur vers l’objet alloué. L’argument hint permet d’aider certains allocateurs à améliorer la localité de référence. Un choix valide est l’adresse d’un objet précédemment alloué par le même objet allocateur et pas encore désalloué. Si vous ne voulez pas fournir d’argument hint, utilisez plutôt un argument de pointeur null.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_allocate.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<int> v1Alloc;    
   allocator<int>::pointer v1aPtr;    
   v1aPtr = v1Alloc.allocate ( 10 );  
  
   int i;  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      v1aPtr[ i ] = i;  
   }  
  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      cout << v1aPtr[ i ] << " ";  
   }  
   cout << endl;    
   v1Alloc.deallocate( v1aPtr, 10 );  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
##  <a name="a-nameallocatorallocatora--allocatorallocator"></a><a name="allocator__allocator"></a>  allocator::allocator  
 Constructeurs utilisés pour créer des objets allocateur.  
  
```  
allocator();
allocator(const allocator<Type>& right);
template <class Other>  
allocator(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Objet allocateur à copier.  
  
### <a name="remarks"></a>Notes  
 Le constructeur n’effectue aucune opération. En général, toutefois, un objet allocateur construit à partir d’un autre objet allocateur doit avoir la même valeur et autoriser l’échange d’allocation et de libération d’objets entre les deux objets allocateur.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_allocator.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int( int i )   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <Int>:: allocator_type v1Alloc;  
  
   allocator<double> cAlloc(Alloc);   
   allocator<Int> cv1Alloc(v1Alloc);  
  
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
  
##  <a name="a-nameallocatorconstpointera--allocatorconstpointer"></a><a name="allocator__const_pointer"></a>  allocator::const_pointer  
 Type qui fournit un pointeur constant vers le type d'objet géré par l'allocateur.  
  
```  
typedef const value_type *const_pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type pointeur décrit un objet **ptr** qui peut désigner, par l’expression ** \*ptr**, tout objet const qu’un objet de classe de modèle allocator peut allouer.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_const_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 10;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer's address found has a value of: "  
        << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer's address found has a value of: 10.  
```  
  
##  <a name="a-nameallocatorconstreferencea--allocatorconstreference"></a><a name="allocator__const_reference"></a>  allocator::const_reference  
 Type qui fournit une référence constante au type d'objet géré par l'allocateur.  
  
```  
typedef const value_type& const_reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type référence décrit un objet qui peut désigner tout objet const qu’un objet de classe de modèle allocator peut allouer.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_const_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::const_reference vcref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vcref << ",\n the first element in the vector." << endl;  
  
   // const references can have their elements modified,  
   // so the following would generate an error:  
   // vcref = 150;  
   // but the value of the first element could be modified through  
   // its nonconst iterator and the const reference would remain valid  
 *vfIter = 175;  
   cout << "The value of the element referred to by vcref,"  
        <<"\n after nofication through its nonconst iterator, is: "  
        << vcref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The value of the element referred to by vcref,  
 after nofication through its nonconst iterator, is: 175.  
```  
  
##  <a name="a-nameallocatorconstructa--allocatorconstruct"></a><a name="allocator__construct"></a>  allocator::construct  
 Construit un type d'objet spécifique à une adresse spécifiée qui est initialisée avec une valeur spécifiée.  
  
```  
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>  
void construct(pointer ptr, _Other&&...   val);
```  
  
### <a name="parameters"></a>Paramètres  
 ` ptr`  
 Pointeur vers l’emplacement où l’objet doit être construit.  
  
 ` val`  
 Valeur avec laquelle l’objet en cours de construction doit être initialisé.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre est équivalente à **new** ((`void` \*) ` ptr`) **Type** (` val`).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_construct.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 6, kB = 7;  
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The modified vector v1 is:  
 ( 3 7 9 12 15 18 21 ).  
```  
  
##  <a name="a-nameallocatordeallocatea--allocatordeallocate"></a><a name="allocator__deallocate"></a>  allocator::deallocate  
 Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.  
  
```  
void deallocate(pointer ptr, size_type count);
```  
  
### <a name="parameters"></a>Paramètres  
 ` ptr`  
 Pointeur vers le premier objet à désallouer dans le stockage.  
  
 ` count`  
 Nombre d’objets à désallouer dans le stockage.  
  
### <a name="remarks"></a>Notes  
 La fonction membre libère du stockage pour le tableau d’objets count de type **Type** à partir de ` ptr`, en appelant `operator delete`(` ptr`). Le pointeur ` ptr` doit avoir été retourné précédemment par un appel à [allocate](#allocator__allocate) pour un objet allocateur dont la valeur est égale à **\*this**, en allouant un objet tableau de même taille et de même type. `deallocate` ne lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple utilisant la fonction membre, consultez [allocator::allocate](#allocator__allocate).  
  
##  <a name="a-nameallocatordestroya--allocatordestroy"></a><a name="allocator__destroy"></a>  allocator::destroy  
 Appelle un destructeur d'objets sans libérer la mémoire où l'objet était stocké.  
  
```  
void destroy(pointer ptr);
```  
  
### <a name="parameters"></a>Paramètres  
 ` ptr`  
 Pointeur désignant l’adresse de l’objet à détruire.  
  
### <a name="remarks"></a>Notes  
 La fonction membre détruit l’objet désigné par ` ptr`, en appelant le destructeur ` ptr` -> **Type**:: **~Type**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_destroy.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 12, kB = -99;  
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The modified vector v1 is:  
 ( 2 4 6 8 10 -99 14 ).  
```  
  
##  <a name="a-nameallocatordifferencetypea--allocatordifferencetype"></a><a name="allocator__difference_type"></a>  allocator::difference_type  
 Type intégral signé qui peut représenter la différence entre des valeurs de pointeurs vers le type d'objet géré par l'allocateur.  
  
```  
typedef ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type d’entier signé décrit un objet qui peut représenter la différence entre les adresses de deux éléments dans une séquence qu’un objet de classe de modèle allocator peut allouer.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_diff_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 0 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1PtrA, v1PtrB;  
   const int kA = 4, kB =12;  
   v1PtrA = v1Alloc.address( kA );  
   v1PtrB = v1Alloc.address( kB );  
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;  
  
   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;  
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;  
   cout << "The difference between the integer's addresses is: "  
        << v1diff << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 0 2 4 6 8 10 12 14 ).  
Pointer v1PtrA addresses 4.  
Pointer v1PtrB addresses 12.  
The difference between the integer's addresses is: 8.  
```  
  
##  <a name="a-nameallocatormaxsizea--allocatormaxsize"></a><a name="allocator__max_size"></a>  allocator::max_size  
 Retourne le nombre d’éléments de type **Type** qui pourraient être alloués par un objet de classe allocator avant que la mémoire libre soit complètement utilisée.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments pouvant être alloués.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_max_size.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   vector <double> v2;  
   vector <double> ::iterator v2Iter;  
   vector <double> :: allocator_type v2Alloc;  
   allocator<int>::size_type v1size;  
   v1size = v1Alloc.max_size( );  
  
   cout << "The number of integers that can be allocated before\n"  
        << " the free memory in the vector v1 is used up is: "  
        << v1size << "." << endl;  
  
   int ii;  
   for ( ii = 1 ; ii <= 7 ; ii++ )  
   {  
      v2.push_back( ii * 10.0 );  
   }  
  
   cout << "The original vector v2 is:\n ( " ;  
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )  
      cout << *v2Iter << " ";  
   cout << ")." << endl;  
   allocator<double>::size_type v2size;  
   v2size = v2Alloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v2 is used up is: "  
        << v2size << "." << endl;  
}  
```  
  
##  <a name="a-nameallocatoroperatoreqa--allocatoroperator"></a><a name="allocator__operator_eq"></a>  allocator::operator=  
 Assigne un objet allocateur à un autre objet allocateur.  
  
```  
template <class Other>  
allocator<Type>& operator=(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Objet allocateur à assigner à un autre objet allocateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet allocateur  
  
### <a name="remarks"></a>Notes  
 L’opérateur d’assignation de modèle n’effectue aucune opération. En général, toutefois, un objet allocateur assigné à un autre objet allocateur doit avoir la même valeur et autoriser l’échange d’allocation et de libération d’objets entre les deux objets allocateur.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_op_assign.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( ) {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<Int> Alloc;  
   allocator<Int> cAlloc ;  
   cAlloc = Alloc;      
}  
```  
  
##  <a name="a-nameallocatorpointera--allocatorpointer"></a><a name="allocator__pointer"></a>  allocator::pointer  
 Type qui fournit un pointeur vers le type d'objet géré par l'allocateur.  
  
```  
typedef value_type *pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type pointeur décrit un objet **ptr** qui peut désigner, par l’expression **\*ptr**, tout objet qu’un objet de classe de modèle allocator peut allouer.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 12;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;     
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.  
```  
  
##  <a name="a-nameallocatorrebinda--allocatorrebind"></a><a name="allocator__rebind"></a>  allocator::rebind  
 Structure qui permet à un allocateur d'objets d'un type d'allouer du stockage pour les objets d'un autre type.  
```  
struct rebind {    typedef allocator<_Other> other ;    };  
```  
### <a name="parameters"></a>Paramètres  
 *other*  
 Type d’élément pour lequel la mémoire est allouée.  
  
### <a name="remarks"></a>Notes  
 Cette structure est utile pour allouer de la mémoire au type qui diffère du type d’élément du conteneur en cours d’implémentation.  
  
 La classe de modèle membre définit le type other. Son seul but est de fournir le nom du type **allocator**\<_ **Other**>, étant donné le nom de type **allocator**\< **Type**>.  
  
 Par exemple, étant donné un objet allocateur **al** de type **A**, vous pouvez allouer un objet de type **_Other** avec l’expression :  
  
```  
A::rebind<Other>::other(al).allocate(1, (Other *)0)  
```  
  
 Sinon, vous pouvez nommer son type pointeur en écrivant le type :  
  
```  
A::rebind<Other>::other::pointer  
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_rebind.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
typedef vector<int>::allocator_type IntAlloc;  
int main( )   
{  
   IntAlloc v1Iter;  
   vector<int> v1;  
  
   IntAlloc::rebind<char>::other::pointer pszC =  
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);  
  
   int * pInt = v1Iter.allocate(10);  
}  
```  
  
##  <a name="a-nameallocatorreferencea--allocatorreference"></a><a name="allocator__reference"></a>  allocator::reference  
 Type qui fournit une référence au type d'objet géré par l'allocateur.  
  
```  
typedef value_type& reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type référence décrit un objet qui peut désigner tout objet qu’un objet de la classe de modèle allocator peut allouer.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_reference.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::reference vref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vref << ",\n the first element in the vector." << endl;  
  
   // nonconst references can have their elements modified  
   vref = 150;  
   cout << "The element referred to by vref after being modified is: "  
        << vref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The element referred to by vref after being modified is: 150.  
```  
  
##  <a name="a-nameallocatorsizetypea--allocatorsizetype"></a><a name="allocator__size_type"></a>  allocator::size_type  
 Type intégral non signé qui peut représenter la longueur d’une séquence qu’un objet de la classe de modèle allocator peut allouer.  
  
```  
typedef size_t size_type;  
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_size_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v;  
   vector <double> ::iterator vIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   allocator<double>::size_type vsize;  
   vsize = vAlloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v is used up is: "  
        << vsize << "." << endl;  
}  
```  
  
##  <a name="a-nameallocatorvaluetypea--allocatorvaluetype"></a><a name="allocator__value_type"></a>  allocator::value_type  
 Type géré par l'allocateur.  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **Type**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// allocator_value_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::value_type vecVal = 150.0;  
 *vfIter = vecVal;  
   cout << "The value of the element addressed by vfIter is: "  
        << *vfIter << ",\n the first element in the vector." << endl;  
  
   cout << "The modified vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element addressed by vfIter is: 150,  
 the first element in the vector.  
The modified vector v is:  
 ( 150 200 300 400 500 600 700 ).  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


