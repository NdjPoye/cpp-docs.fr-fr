---
title: list, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.list
- list
- std::list
- list/std::list
dev_langs:
- C++
helpviewer_keywords:
- list class
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: 20
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
ms.openlocfilehash: 16d9bb63aac40bc4494f8d748fd752cde85d79d9
ms.lasthandoff: 02/24/2017

---
# <a name="list-class"></a>list, classe
La classe list de la bibliothèque standard C++ est une classe de modèle de conteneurs de séquences qui conservent leurs éléments dans une disposition linéaire et permettent d’effectuer des insertions et des suppressions efficaces à n’importe quel emplacement de la séquence. La séquence est stockée sous forme de liste liée bidirectionnelle d’éléments, chacun contenant un membre d’un type *Type*.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
template <class Type, class Allocator= allocator<Type>>  
class list  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type*  
 Type de données d'élément à stocker dans la liste.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la libération de mémoire de la liste. Cet argument est facultatif et sa valeur par défaut est **allocator**\< *Type*> *.*  
  
## <a name="remarks"></a>Remarques  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application. Les vecteurs doivent être le conteneur par défaut pour la gestion d'une séquence quand l'accès aléatoire à n'importe quel élément est primordial et que des insertions ou des suppressions d'éléments sont seulement nécessaires à la fin d'une séquence. Les performances du conteneur de classe deque sont supérieures quand l'accès aléatoire est nécessaire, et que les insertions et suppressions au début et à la fin d'une séquence sont cruciales.  
  
 Les fonctions membres de liste [merge](#list__merge), [reverse](#list__reverse), [unique](#list__unique), [remove](#list__remove) et [remove_if](#list__remove_if) ont été optimisées pour le traitement des objets de liste. Elles offrent une alternative de haute performance à leurs homologues génériques.  
  
 La réallocation de liste se produit quand une fonction membre doit insérer ou effacer des éléments de la liste. Dans ce cas, seuls les itérateurs ou les références qui pointent vers les parties effacées de la séquence contrôlée deviennent non valides.  
  
 Incluez l’en-tête standard de bibliothèque standard C++ \<list> pour définir la liste de classe de modèle [container](../standard-library/stl-containers.md) et plusieurs modèles de prise en charge.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[list](#list__list)|Construit une liste de taille spécifique ou contenant des éléments de valeurs spécifiques, ou contenant un `allocator` spécifique ou comme copie d'une autre liste.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#list__allocator_type)|Type qui représente la classe `allocator` d'un objet list.|  
|[const_iterator](#list__const_iterator)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans une liste.|  
|[const_pointer](#list__const_pointer)|Type qui fournit un pointeur vers un élément `const` dans une liste.|  
|[const_reference](#list__const_reference)|Type qui fournit une référence à un élément `const` stocké dans une liste pour la lecture et l'exécution des opérations `const`.|  
|[const_reverse_iterator](#list__const_reverse_iterator)|Type qui fournit un itérateur bidirectionnel capable de lire un élément `const` dans une liste.|  
|[difference_type](#list__difference_type)|Type qui fournit la différence entre deux itérateurs qui font référence aux éléments d'une même liste.|  
|[iterator](#list__iterator)|Type qui fournit un itérateur bidirectionnel capable de lire ou modifier un élément d'une liste.|  
|[pointer](#list__pointer)|Type qui fournit un pointeur vers un élément d'une liste.|  
|[reference](#list__reference)|Type qui fournit une référence à un élément `const` stocké dans une liste pour la lecture et l'exécution des opérations `const`.|  
|[reverse_iterator](#list__reverse_iterator)|Type qui fournit un itérateur bidirectionnel pouvant lire ou modifier un élément d'une liste inversée.|  
|[size_type](#list__size_type)|Type qui compte le nombre d'éléments dans une liste.|  
|[value_type](#list__value_type)|Type qui représente le type de données stocké dans une liste.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[assign](#list__assign)|Efface les éléments d'une liste et copie un nouvel ensemble d'éléments dans la liste cible.|  
|[back](#list__back)|Retourne une référence au dernier élément d'une liste.|  
|[begin](#list__begin)|Retourne un itérateur qui traite le premier élément d'une liste.|  
|[list::cbegin](#list__cbegin)|Retourne un itérateur const qui traite le premier élément d'une liste.|  
|[list::cend](#list__cend)|Retourne un itérateur const qui traite l'emplacement situé après le dernier élément d'une liste.|  
|[list::clear](#list__clear)|Efface tous les éléments d'une liste.|  
|[list::crbegin](#list__crbegin)|Retourne un itérateur const qui traite le premier élément d'une liste inversée.|  
|[list::crend](#list__crend)|Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'une liste inversée.|  
|[list::emplace](#list__emplace)|Insère un élément construit en place dans une liste à la position spécifiée.|  
|[list::emplace_back](#list__emplace_back)|Ajoute un élément construit sur place à la fin d'une liste.|  
|[list::emplace_front](#list__emplace_front)|Ajoute un élément construit sur place au début d'une liste.|  
|[empty](#list__empty)|Vérifie si une liste est vide.|  
|[end](#list__end)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une liste.|  
|[erase](#list__erase)|Supprime un élément ou une plage d'éléments d'une liste aux emplacements spécifiés.|  
|[front](#list__front)|Retourne une référence au premier élément d'une liste.|  
|[get_allocator](#list__get_allocator)|Retourne une copie de l'objet `allocator` utilisé pour construire une liste.|  
|[insert](#list__insert)|Insère un élément, un certain nombre d'éléments ou une plage d'éléments dans une liste à la position spécifiée.|  
|[max_size](#list__max_size)|Retourne la longueur maximale d'une liste.|  
|[merge](#list__merge)|Supprime les éléments de la liste d'arguments, les insère dans la liste cible, puis classe le nouvel ensemble combiné d'éléments dans l'ordre croissant ou dans un autre ordre spécifique.|  
|[pop_back](#list__pop_back)|Supprime l'élément à la fin d'une liste.|  
|[pop_front](#list__pop_front)|Supprime l'élément au début d'une liste.|  
|[push_back](#list__push_back)|Ajoute un élément à la fin d'une liste.|  
|[push_front](#list__push_front)|Ajoute un élément au début d'une liste.|  
|[rbegin](#list__rbegin)|Retourne un itérateur qui traite le premier élément d'une liste inversée.|  
|[remove](#list__remove)|Efface les éléments d'une liste qui correspondent à la valeur spécifiée.|  
|[remove_if](#list__remove_if)|Efface les éléments de la liste pour laquelle un prédicat spécifié est satisfait.|  
|[rend](#list__rend)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une liste inversée.|  
|[resize](#list__resize)|Spécifie une nouvelle taille pour une liste.|  
|[reverse](#list__reverse)|Inverse l'ordre dans lequel les éléments apparaissent dans une liste.|  
|[size](#list__size)|Retourne le nombre d'éléments d'une liste.|  
|[sort](#list__sort)|Réorganise les éléments d'une liste dans l'ordre croissant ou en fonction d'une autre relation d'ordre.|  
|[splice](#list__splice)|Supprime des éléments de la liste d’arguments et les insère dans la liste cible.|  
|[swap](#list__swap)|Échange les éléments de deux listes.|  
|[unique](#list__unique)|Supprime les doublons adjacents ou les éléments adjacents qui satisfont un autre prédicat binaire dans la liste.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[list::operator=](#list__operator_eq)|Remplace les éléments de la liste par une copie d'une autre liste.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête** : \<list>  
  
##  <a name="a-namelistallocatortypea--listallocatortype"></a><a name="list__allocator_type"></a>  list::allocator_type  
 Type qui représente la classe d'allocateur d'un objet list.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Remarques  
 `allocator_type` est un synonyme du paramètre de modèle **Allocator.**  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [get_allocator](#list__get_allocator).  
  
##  <a name="a-namelistassigna--listassign"></a><a name="list__assign"></a>  list::assign  
 Efface les éléments d'une liste et copie un nouvel ensemble d'éléments dans une liste cible.  
  
```  
void assign(
    size_type Count,  
    const Type& Val);

void assign  
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);
```  
  
### <a name="parameters"></a>Paramètres  
 `First`  
 Position du premier élément de la plage d’éléments à copier à partir de la liste d’arguments.  
  
 `Last`  
 Position du premier élément juste après la plage d'éléments à copier à partir de la liste d'arguments.  
  
 `Count`  
 Nombre de copies d'un élément inséré dans la liste.  
  
 `Val`  
 Valeur de l'élément inséré dans la liste.  
  
 `IList`  
 initializer_list qui contient les éléments à insérer.  
  
### <a name="remarks"></a>Remarques  
 Après avoir effacé les éléments existants dans la liste cible, assign insère la plage d'éléments spécifiée à partir de la liste d'origine ou d'une autre liste dans la liste cible, ou insère des copies d'un nouvel élément ayant la valeur spécifiée dans la liste cible.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_assign.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    list<int> c1, c2;  
    list<int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign({ 10, 20, 30, 40 });  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 10 20 30c1 = 50 60c1 = 4 4 4 4 4 4 4c1 = 10 20 30 40  
```  
  
##  <a name="a-namelistbacka--listback"></a><a name="list__back"></a>  list::back  
 Retourne une référence au dernier élément d'une liste.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Dernier élément de la liste. Si la liste est vide, la valeur de retour n'est pas définie.  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de retour de **back** est affectée à un objet `const_reference`, l’objet de liste ne peut pas être changé. Si la valeur de retour de **back** est affectée à un objet **reference**, l’objet de liste peut être changé.  
  
 En cas de compilation avec [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) défini sur 1 ou 2, une erreur d’exécution se produit si vous essayez d’accéder à un élément d’une liste vide.  Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="a-namelistbegina--listbegin"></a><a name="list__begin"></a>  list::begin  
 Retourne un itérateur qui traite le premier élément d'une liste.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel qui traite le premier élément dans la liste ou à l'emplacement qui suit une liste vide.  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de retour de **begin** est affectée à un objet `const_iterator`, les éléments de l’objet de liste ne peuvent pas être changés. Si la valeur de retour de **begin** est affectée à un objet **iterator**, les éléments de l’objet de liste peuvent être changés.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_begin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="a-namelistcbegina--listcbegin"></a><a name="list__cbegin"></a>  list::cbegin  
 Retourne un itérateur `const` qui traite le premier élément d'une plage.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur forward bidirectionnel `const` qui pointe vers le premier élément de la plage, ou vers l'emplacement situé juste après la fin d'une plage vide (pour une plage vide : `cbegin() == cend()`).  
  
### <a name="remarks"></a>Notes  
 Avec la valeur de retour `cbegin`, les éléments de la plage ne peuvent pas être modifiés.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `begin()` afin de garantir que la valeur de retour est `const_iterator`. En général, elle est utilisée conjointement au mot clé de déduction de type [auto](../cpp/auto-cpp.md), comme le montre l’exemple suivant. Dans cet exemple, il est supposé que `Container` est un conteneur modifiable (autre que `const`) de tout type prenant en charge `begin()` et `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namelistcenda--listcend"></a><a name="list__cend"></a>  list::cend  
 Retourne un itérateur `const` qui traite l'emplacement situé immédiatement après le dernier élément d'une plage.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur forward bidirectionnel `const` qui pointe juste après la fin de la plage.  
  
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
  
##  <a name="a-namelistcleara--listclear"></a><a name="list__clear"></a>  list::clear  
 Efface tous les éléments d'une liste.  
  
```  
void clear();
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_clear.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the list is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of list after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the list is initially 3  
The size of list after clearing is 0  
```  
  
##  <a name="a-namelistconstiteratora--listconstiterator"></a><a name="list__const_iterator"></a>  list::const_iterator  
 Type qui fournit un itérateur bidirectionnel capable de lire un élément **const** dans une liste.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Remarques  
 Un type `const_iterator` ne peut pas être utilisé pour changer la valeur d'un élément.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [back](#list__back).  
  
##  <a name="a-namelistconstpointera--listconstpointer"></a><a name="list__const_pointer"></a>  list::const_pointer  
 Fournit un pointeur vers un élément `const` dans une liste.  
  
``` 
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Remarques  
 Un type `const_pointer` ne peut pas être utilisé pour changer la valeur d'un élément.  
  
 Dans la plupart des cas, vous devez utiliser un [iterator](#list__iterator) pour accéder aux éléments dans un objet de liste.  
  
##  <a name="a-namelistconstreferencea--listconstreference"></a><a name="list__const_reference"></a>  list::const_reference  
 Type qui fournit une référence à un élément **const** stocké dans une liste pour la lecture et l’exécution d’opérations **const**.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Remarques  
 Un type `const_reference` ne peut pas être utilisé pour changer la valeur d'un élément.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_const_ref.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const list <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error because c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namelistconstreverseiteratora--listconstreverseiterator"></a><a name="list__const_reverse_iterator"></a>  list::const_reverse_iterator  
 Type qui fournit un itérateur bidirectionnel capable de lire un élément **const** dans une liste.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarques  
 Un type `const_reverse_iterator` ne peut pas changer la valeur d'un élément. Il sert à itérer la liste dans l'ordre inverse.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [rbegin](#list__rbegin).  
  
##  <a name="a-namelistcrbegina--listcrbegin"></a><a name="list__crbegin"></a>  list::crbegin  
 Retourne un itérateur const qui traite le premier élément d'une liste inversée.  
  
```  
const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel inversé const qui traite le premier élément d’une liste inversée (ou qui traite ce qui était le dernier élément de l’objet `list` non inversé).  
  
### <a name="remarks"></a>Remarques  
 `crbegin` est utilisé avec une liste inversée de la même manière que [list::begin](#list__begin) est utilisé avec un objet `list`.  
  
 Avec la valeur de retour `crbegin`, l'objet de liste ne peut pas être changé. [list::rbegin](#list__rbegin) peut servir à itérer une liste vers l’arrière.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_crbegin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::const_reverse_iterator c1_crIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1_crIter = c1.crbegin( );  
   cout << "The last element in the list is " << *c1_crIter << "." << endl;  
}  
```  
  
```Output  
The last element in the list is 30.  
```  
  
##  <a name="a-namelistcrenda--listcrend"></a><a name="list__crend"></a>  list::crend  
 Retourne un itérateur const qui traite l'emplacement qui suit le dernier élément d'une liste inversée.  
  
```  
const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel inversé const qui traite l’emplacement qui suit le dernier élément d’un objet [list](../standard-library/list-class.md) inversé (emplacement qui précédait le premier élément de l’objet `list` non inversé).  
  
### <a name="remarks"></a>Remarques  
 `crend` est utilisé avec une liste inversée de la même manière que [list::end](#list__end) est utilisé avec un objet `list`.  
  
 Avec la valeur de retour `crend`, l'objet `list` ne peut pas être changé.  
  
 `crend` peut être utilisé pour déterminer si un itérateur inversé a atteint la fin de son objet `list`.  
  
 La valeur retournée par `crend` ne doit pas être déréférencée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_crend.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::const_reverse_iterator c1_crIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_crIter = c1.crend( );  
   c1_crIter --;  // Decrementing a reverse iterator moves it forward in   
                 // the list (to point to the first element here)  
   cout << "The first element in the list is: " << *c1_crIter << endl;  
}  
```  
  
```Output  
The first element in the list is: 10  
```  
  
##  <a name="a-namelistdifferencetypea--listdifferencetype"></a><a name="list__difference_type"></a>  list::difference_type  
 Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'une liste au sein d'une plage, parmi les éléments pointés par les itérateurs.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Remarques  
 `difference_type` est le type retourné durant la soustraction ou l'incrémentation via les itérateurs du conteneur. `difference_type` est généralement utilisé pour représenter le nombre d’éléments de la plage [ ` first`, ` last`) entre les itérateurs ` first` et ` last`. Il inclut l’élément vers lequel pointe ` first` et la plage d’éléments allant jusqu’à l’élément (mais sans l’inclure) vers lequel pointe ` last`.  
  
 Notez que même si `difference_type` est disponible pour tous les itérateurs qui répondent aux exigences d’un itérateur d’entrée, ce qui inclut la classe des itérateurs bidirectionnels prise en charge par les conteneurs réversibles tels que set, la soustraction entre les itérateurs n’est prise en charge que par les itérateurs à accès aléatoire fournis par un conteneur à accès aléatoire, par exemple la [classe vector](../standard-library/vector-class.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <list>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   list <int> c1;  
   list <int>::iterator   c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
    list <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namelistemplacea--listemplace"></a><a name="list__emplace"></a>  list::emplace  
 Insère un élément construit en place dans une liste à la position spécifiée.  
  
```  
void emplace_back(iterator Where, Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Where`|Position dans l’objet [liste](../standard-library/list-class.md) cible où le premier élément est inséré.|  
|` val`|Élément ajouté à la fin de l'objet `list`.|  
  
### <a name="remarks"></a>Remarques  
 Si une exception est levée, l'objet `list` n'est pas modifié et l'exception est levée de nouveau.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_emplace.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace(c2.begin(), move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="a-namelistemplacebacka--listemplaceback"></a><a name="list__emplace_back"></a>  list::emplace_back  
 Ajoute un élément construit sur place au début d'une liste.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|Élément ajouté à la fin de l’objet [list](../standard-library/list-class.md).|  
  
### <a name="remarks"></a>Remarques  
 Si une exception est levée, l'objet `list` n'est pas modifié et l'exception est levée de nouveau.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_emplace_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace_back( move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="a-namelistemplacefronta--listemplacefront"></a><a name="list__emplace_front"></a>  list::emplace_front  
 Ajoute un élément construit sur place au début d'une liste.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|Élément ajouté au début de l’objet [list](../standard-library/list-class.md).|  
  
### <a name="remarks"></a>Remarques  
 Si une exception est levée, l'objet `list` n'est pas modifié et l'exception est levée de nouveau.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_emplace_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="a-namelistemptya--listempty"></a><a name="list__empty"></a>  list::empty  
 Vérifie si une liste est vide.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la liste est vide. **false** si la liste n’est pas vide.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_empty.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The list is empty." << endl;  
   else  
      cout << "The list is not empty." << endl;  
}  
```  
  
```Output  
The list is not empty.  
```  
  
##  <a name="a-namelistenda--listend"></a><a name="list__end"></a>  list::end  
 Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'une liste.  
  
```  
const_iterator end() const;
iterator end();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel qui traite l'emplacement suivant le dernier élément d'une liste. Si la liste est vide, puis `list::end == list::begin`.  
  
### <a name="remarks"></a>Remarques  
 **end** est utilisé pour déterminer si un itérateur a atteint la fin de sa liste.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_end.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is "  
        << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // list <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The list is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The list is now: 10 400 30  
```  
  
##  <a name="a-namelisterasea--listerase"></a><a name="list__erase"></a>  list::erase  
 Supprime un élément ou une plage d'éléments d'une liste aux emplacements spécifiés.  
  
```  
iterator erase(iterator Where);
iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>Paramètres  
 `Where`  
 Position de l'élément à supprimer de la liste.  
  
 ` first`  
 Position du premier élément supprimé de la liste.  
  
 ` last`  
 Position juste après le dernier élément supprimé de la liste.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel qui désigne le premier élément restant après tous les éléments supprimés, ou pointeur vers la fin de la liste si aucun élément de ce genre n'existe.  
  
### <a name="remarks"></a>Remarques  
 Aucune réallocation ne se produit. Ainsi, les itérateurs et les références deviennent non valides uniquement pour les éléments effacés.  
  
 **erase** ne lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_erase.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial list is:";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the list becomes:";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, the list becomes: ";  
   for (Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is: 10 20 30 40 50  
After erasing the first element, the list becomes: 20 30 40 50  
After erasing all elements but the first, the list becomes:  20  
```  
  
##  <a name="a-namelistfronta--listfront"></a><a name="list__front"></a>  list::front  
 Retourne une référence au premier élément d'une liste.  
  
```  
reference front();
const_reference front() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si la liste est vide, la valeur de retour n'est pas définie.  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de retour de `front` est affectée à `const_reference`, l'objet de liste ne peut pas être changé. Si la valeur de retour de `front` est affectée à un objet **reference**, l’objet de liste peut être changé.  
  
 En cas de compilation avec [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) défini sur 1 ou 2, une erreur d’exécution se produit si vous essayez d’accéder à un élément d’une liste vide.  Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
  
   int& i = c1.front();  
   const int& ii = c1.front();  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The first integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The first integer of c1 is 11  
```  
  
##  <a name="a-namelistgetallocatora--listgetallocator"></a><a name="list__get_allocator"></a>  list::get_allocator  
 Retourne une copie de l'objet allocateur utilisé pour construire une liste.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Allocateur utilisé par la liste.  
  
### <a name="remarks"></a>Remarques  
 Les allocateurs de la classe de liste spécifient la façon dont la classe gère le stockage. Les allocateurs par défaut fournis avec les classes de conteneur de la bibliothèque standard C++ sont suffisants pour la plupart des besoins en programmation. L'écriture et l'utilisation de votre propre classe d'allocateur font l'objet d'une rubrique avancée du langage C++.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_get_allocator.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects   
   // that use the default allocator.  
   list <int> c1;  
   list <int, allocator<int> > c2 = list <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   list <int> c3( c1.get_allocator( ) );  
  
   list<int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namelistinserta--listinsert"></a><a name="list__insert"></a>  list::insert  
 Insère un élément, un certain nombre d'éléments ou une plage d'éléments dans une liste à la position spécifiée.  
  
```  
iterator insert(iterator Where, const Type& Val);
iterator insert(iterator Where, Type&& Val);

void insert(iterator Where, size_type Count, const Type& Val);
iterator insert(iterator Where, initializer_list<Type> IList);

template <class InputIterator>  
void insert(iterator Where, InputIterator First, InputIterator Last);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Where`|Position dans la liste cible où le premier élément est inséré.|  
|`Val`|Valeur de l'élément inséré dans la liste.|  
|`Count`|Nombre d'éléments insérés dans la liste.|  
|`First`|Position du premier élément de la plage d'éléments dans la liste d'arguments à copier.|  
|`Last`|Position du premier élément au-delà de la plage d’éléments dans la liste d’arguments à copier.|  
  
### <a name="return-value"></a>Valeur de retour  
 Les deux premières fonctions insert retournent un itérateur qui pointe vers la position où le nouvel élément a été inséré dans la liste.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_class_insert.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    list <int> c1, c2;  
    list <int>::iterator Iter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    Iter = c1.begin();  
    Iter++;  
    c1.insert(Iter, 100);  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    Iter = c1.begin();  
    Iter++;  
    Iter++;  
    c1.insert(Iter, 2, 200);  
  
    cout << "c1 =";  
    for(auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.insert(++c1.begin(), c2.begin(), --c2.end());  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    // initialize a list of strings by moving  
    list < string > c3;  
    string str("a");  
  
    c3.insert(c3.begin(), move(str));  
    cout << "Moved first element: " << c3.front() << endl;  
  
    // Assign with an initializer_list  
    list <int> c4{ {1, 2, 3, 4} };  
    c4.insert(c4.begin(), { 5, 6, 7, 8 });  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
##  <a name="a-namelistiteratora--listiterator"></a><a name="list__iterator"></a>  list::iterator  
 Type qui fournit un itérateur bidirectionnel capable de lire ou modifier un élément d'une liste.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser un type **iterator** pour modifier la valeur d’un élément.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [begin](#list__begin).  
  
##  <a name="a-namelistlista--listlist"></a><a name="list__list"></a>  list::list  
 Construit une liste de taille spécifique ou contenant des éléments de valeurs spécifiques, ou contenant un allocateur spécifique ou comme copie complète ou partielle d'une autre liste.  
  
```  
list();
explicit list(const Allocator& Al);
explicit list(size_type Count);
list(size_type Count, const Type& Val);
list(size_type Count, const Type& Val, const Allocator& Al);

list(const list& Right);
list(list&& Right);
list(initializer_list<Type> IList, const Allocator& Al);

template <class InputIterator>  
list(InputIterator First, InputIterator Last);

template <class InputIterator>  
list(InputIterator First, InputIterator Last, const Allocator& Al);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Al`|Classe allocator à utiliser avec cet objet.|  
|`Count`|Nombre d'éléments dans la liste construite.|  
|`Val`|Valeur des éléments de la liste.|  
|`Right`|Liste dont la liste construite doit être une copie.|  
|`First`|Position du premier élément de la plage d'éléments à copier.|  
|`Last`|Position du premier élément au-delà de la plage d'éléments à copier.|  
|`IList`|initializer_list qui contient les éléments à copier.|  
  
### <a name="remarks"></a>Remarques  
 Tous les constructeurs stockent un objet allocateur ( `Al`) et initialisent la liste.  
  
 [get_allocator](#list__get_allocator) retourne une copie de l’objet allocateur utilisé pour construire une liste.  
  
 Les deux premiers constructeurs spécifient une liste initiale vide. En outre, le second spécifie le type d’allocateur ( `Al`) à utiliser.  
  
 Le troisième constructeur spécifie une répétition d'un nombre spécifique ( `Count`) d'éléments de la valeur par défaut pour la classe **Type**.  
  
 Les quatrième et cinquième constructeurs spécifient une répétition de ( `Count`) éléments ayant la valeur `Val`.  
  
 Le sixième constructeur spécifie une copie de la liste `Right`.  
  
 Le septième constructeur déplace la liste `Right`.  
  
 Le huitième constructeur utilise initializer_list pour spécifier les éléments.  
  
 Les deux constructeurs suivants copient la plage `[First, Last)` d'une liste.  
  
 Aucun des constructeurs n'effectue de réallocations temporaires.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_class_list.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    // Create an empty list c0  
    list <int> c0;  
  
    // Create a list c1 with 3 elements of default value 0  
    list <int> c1(3);  
  
    // Create a list c2 with 5 elements of value 2  
    list <int> c2(5, 2);  
  
    // Create a list c3 with 3 elements of value 1 and with the   
    // allocator of list c2  
    list <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, list c4, of list c2  
    list <int> c4(c2);  
  
    // Create a list c5 by copying the range c4[ first,  last)  
    list <int>::iterator c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    list <int> c5(c4.begin(), c4_Iter);  
  
    // Create a list c6 by copying the range c4[ first,  last) and with   
    // the allocator of list c2  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    list <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c2 =";  
    for (auto c : c2)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c3 =";  
    for (auto c : c3)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c5 =";  
    for (auto c : c5)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c6 =";  
    for (auto c : c6)  
        cout << " " << c;  
    cout << endl;  
  
    // Move list c6 to list c7  
    list <int> c7(move(c6));  
    cout << "c7 =";  
    for (auto c : c7)  
        cout << " " << c;  
    cout << endl;  
  
    // Construct with initializer_list  
    list<int> c8({ 1, 2, 3, 4 });  
    cout << "c8 =";  
    for (auto c : c8)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 0 0 0c2 = 2 2 2 2 2c3 = 1 1 1c4 = 2 2 2 2 2c5 = 2 2c6 = 2 2 2c7 = 2 2 2c8 = 1 2 3 4  
```  
  
##  <a name="a-namelistmaxsizea--listmaxsize"></a><a name="list__max_size"></a>  list::max_size  
 Retourne la longueur maximale d'une liste.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Longueur maximale autorisée de la liste.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_max_size.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "Maximum possible length of the list is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namelistmergea--listmerge"></a><a name="list__merge"></a>  list::merge  
 Supprime les éléments de la liste d'arguments, les insère dans la liste cible, puis classe le nouvel ensemble combiné d'éléments dans l'ordre croissant ou dans un autre ordre spécifique.  
  
```  
void merge(list<Type, Allocator>& right);

template <class Traits>  
void merge(list<Type, Allocator>& right, Traits comp);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Liste d’arguments à fusionner avec la liste cible.  
  
 ` comp`  
 Opérateur de comparaison utilisé pour classer les éléments de la liste cible.  
  
### <a name="remarks"></a>Remarques  
 La liste d'arguments ` right` est fusionnée avec la liste cible.  
  
 La liste d'arguments et la liste cible doivent être classées en fonction de la même relation de comparaison que la séquence résultante. L'ordre par défaut de la première fonction membre est l'ordre croissant. La deuxième fonction membre impose l’opération de comparaison spécifiée par l’utilisateur ` comp` de la classe **Traits**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_merge.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1, c2, c3;  
   list <int>::iterator c1_Iter, c2_Iter, c3_Iter;  
  
   c1.push_back( 3 );  
   c1.push_back( 6 );  
   c2.push_back( 2 );  
   c2.push_back( 4 );  
   c3.push_back( 5 );  
   c3.push_back( 1 );  
  
   cout << "c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   cout << "c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   c2.merge( c1 );  // Merge c1 into c2 in (default) ascending order  
   c2.sort( greater<int>( ) );  
   cout << "After merging c1 with c2 and sorting with >: c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   cout << "c3 =";  
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
      cout << " " << *c3_Iter;  
   cout << endl;  
  
   c2.merge( c3, greater<int>( ) );  
   cout << "After merging c3 with c2 according to the '>' comparison relation: c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
c1 = 3 6  
c2 = 2 4  
After merging c1 with c2 and sorting with >: c2 = 6 4 3 2  
c3 = 5 1  
After merging c3 with c2 according to the '>' comparison relation: c2 = 6 5 4 3 2 1  
```  
  
##  <a name="a-namelistoperatoreqa--listoperator"></a><a name="list__operator_eq"></a>  list::operator=  
 Remplace les éléments de la liste par une copie d'une autre liste.  
  
```  
list& operator=(const list& right);
list& operator=(list&& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` right`|Objet [list](../standard-library/list-class.md) copié dans `list`.|  
  
### <a name="remarks"></a>Remarques  
 Après avoir effacé les éléments existants dans `list`, l'opérateur copie ou déplace le contenu de ` right` dans `list`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_operator_as.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list<int> v1, v2, v3;  
   list<int>::iterator iter;  
  
   v1.push_back(10);  
   v1.push_back(20);  
   v1.push_back(30);  
   v1.push_back(40);  
   v1.push_back(50);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = forward< list<int> >(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namelistpointera--listpointer"></a><a name="list__pointer"></a>  list::pointer  
 Fournit un pointeur vers un élément dans une liste.  
  
```
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser un type **pointer** pour modifier la valeur d’un élément.  
  
 Dans la plupart des cas, vous devez utiliser un [iterator](#list__iterator) pour accéder aux éléments dans un objet de liste.  
  
##  <a name="a-namelistpopbacka--listpopback"></a><a name="list__pop_back"></a>  list::pop_back  
 Supprime l'élément à la fin d'une liste.  
  
``` 
void pop_back();
```  
  
### <a name="remarks"></a>Remarques  
 Le dernier élément ne doit pas être vide. `pop_back` ne lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_pop_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the list, "  
           "the last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the list, the last element is: 1  
```  
  
##  <a name="a-namelistpopfronta--listpopfront"></a><a name="list__pop_front"></a>  list::pop_front  
 Supprime l'élément au début d'une liste.  
  
``` 
void pop_front();
```  
  
### <a name="remarks"></a>Remarques  
 Le premier élément ne doit pas être vide. `pop_front` ne lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_pop_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the list, "  
         "the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the list, the first element is: 2  
```  
  
##  <a name="a-namelistpushbacka--listpushback"></a><a name="list__push_back"></a>  list::push_back  
 Ajoute un élément à la fin d'une liste.  
  
```  
void push_back(void push_back(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|Élément ajouté à la fin de la liste.|  
  
### <a name="remarks"></a>Remarques  
 Si une exception est levée, la liste reste inchangée et l'exception est levée de nouveau.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_push_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "Last element: " << c1.back( ) << endl;  
  
   c1.push_back( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New last element: " << c1.back( ) << endl;  
  
// move initialize a list of strings  
   list <string> c2;  
   string str("a");  
  
   c2.push_back( move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved first element: a  
```  
  
##  <a name="a-namelistpushfronta--listpushfront"></a><a name="list__push_front"></a>  list::push_front  
 Ajoute un élément au début d'une liste.  
  
```  
void push_front(const Type& val);
void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|Élément ajouté au début de la liste.|  
  
### <a name="remarks"></a>Remarques  
 Si une exception est levée, la liste reste inchangée et l'exception est levée de nouveau.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_push_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a list of strings  
   list <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="a-namelistrbegina--listrbegin"></a><a name="list__rbegin"></a>  list::rbegin  
 Retourne un itérateur qui traite le premier élément d’une liste inversée.  
  
``` 
const_reverse_iterator rbegin() const;
reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel inversé qui traite le premier élément dans une liste inversée (ou qui traite ce qui était le dernier élément dans la liste non inversée).  
  
### <a name="remarks"></a>Remarques  
 `rbegin` est utilisé avec une liste inversée, de la même manière que [begin](#list__begin) est utilisé avec une liste.  
  
 Si la valeur de retour de `rbegin` est affectée à `const_reverse_iterator`, l'objet de liste ne peut pas être changé. Si la valeur de retour de `rbegin` est affectée à un `reverse_iterator`, l’objet de liste peut être changé.  
  
 `rbegin` peut servir à itérer une liste vers l'arrière.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_rbegin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::reverse_iterator c1_rIter;  
  
   // If the following line replaced the line above, *c1_rIter = 40;  
   // (below) would be an error  
   //list <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1_rIter = c1.rbegin( );  
   cout << "The last element in the list is " << *c1_rIter << "." << endl;  
  
   cout << "The list is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   // rbegin can be used to start an iteration through a list in   
   // reverse order  
   cout << "The reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  
   cout << "The last element in the list is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
The last element in the list is 30.  
The list is: 10 20 30  
The reversed list is: 30 20 10  
The last element in the list is now 40.  
```  
  
##  <a name="a-namelistreferencea--listreference"></a><a name="list__reference"></a>  list::reference  
 Type qui fournit une référence à un élément stocké dans une liste.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_ref.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namelistremovea--listremove"></a><a name="list__remove"></a>  list::remove  
 Efface les éléments d'une liste qui correspondent à la valeur spécifiée.  
  
``` 
void remove(const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 ` val`  
 Valeur qui, si elle est contenue dans un élément, entraîne la suppression de cet élément de la liste.  
  
### <a name="remarks"></a>Remarques  
 L’ordre des éléments restants n’est pas affecté.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_remove.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 5 );  
   c1.push_back( 100 );  
   c1.push_back( 5 );  
   c1.push_back( 200 );  
   c1.push_back( 5 );  
   c1.push_back( 300 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.remove( 5 );  
   cout << "After removing elements with value 5, the list becomes c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = 5 100 5 200 5 300  
After removing elements with value 5, the list becomes c2 = 100 200 300  
```  
  
##  <a name="a-namelistremoveifa--listremoveif"></a><a name="list__remove_if"></a>  list::remove_if  
 Efface les éléments d’une liste pour lesquels un prédicat spécifié est satisfait.  
  
``` 
template <class Predicate>  
void remove_if(Predicate pred)  
```  
  
### <a name="parameters"></a>Paramètres  
 ` pred`  
 Prédicat unaire qui, s’il est satisfait par un élément, entraîne la suppression de cet élément de la liste.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_remove_if.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
template <class T> class is_odd : public std::unary_function<T, bool>   
{  
public:  
   bool operator( ) ( T& val )   
   {  
   return ( val % 2 ) == 1;  
   }  
};  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 3 );  
   c1.push_back( 4 );  
   c1.push_back( 5 );  
   c1.push_back( 6 );  
   c1.push_back( 7 );  
   c1.push_back( 8 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.remove_if( is_odd<int>( ) );  
  
   cout << "After removing the odd elements, "  
        << "the list becomes c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = 3 4 5 6 7 8  
After removing the odd elements, the list becomes c2 = 4 6 8  
```  
  
##  <a name="a-namelistrenda--listrend"></a><a name="list__rend"></a>  list::rend  
 Retourne un itérateur qui traite l’emplacement qui suit le dernier élément d’une liste inversée.  
  
``` 
const_reverse_iterator rend() const;
reverse_iterator rend();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur bidirectionnel inversé qui traite l’emplacement qui suit le dernier élément d’une liste inversée (emplacement qui précédait le premier élément de la liste non inversée).  
  
### <a name="remarks"></a>Remarques  
 `rend` est utilisé avec une liste inversée de la même manière que [end](#list__end) est utilisé avec une liste.  
  
 Si la valeur de retour de `rend` est affectée à un `const_reverse_iterator`, l'objet de liste ne peut pas être changé. Si la valeur de retour de `rend` est affectée à un `reverse_iterator`, l’objet de liste peut être changé.  
  
 Vous pouvez utiliser `rend` pour tester si un itérateur inversé a atteint la fin de sa liste.  
  
 La valeur retournée par `rend` ne doit pas être déréférencée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_rend.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error would   
   // have resulted in the line modifying an element (commented below)  
   // because the iterator would have been const  
   // list <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --;  // Decrementing a reverse iterator moves it forward in   
                 // the list (to point to the first element here)  
   cout << "The first element in the list is: " << *c1_rIter << endl;  
  
   cout << "The list is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of the   
   // elements of a reversed list  
   cout << "The reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--;  // Decrementing the reverse iterator moves it backward   
                // in the reversed list (to the last element here)  
  
 *c1_rIter = 40;  // This modification of the last element would have   
                    // caused an error if a const_reverse iterator had   
                    // been declared (as noted above)  
  
   cout << "The modified reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
}  
```  
  
```Output  
The first element in the list is: 10  
The list is: 10 20 30  
The reversed list is: 30 20 10  
The modified reversed list is: 30 20 40  
```  
  
##  <a name="a-namelistresizea--listresize"></a><a name="list__resize"></a>  list::resize  
 Spécifie une nouvelle taille pour une liste.  
  
``` 
void resize(size_type _Newsize);
void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Newsize`  
 Nouvelle taille de la liste.  
  
 ` val`  
 Valeur des nouveaux éléments à ajouter à la liste si la nouvelle taille est supérieure à la taille d’origine. Si la valeur est omise, la valeur par défaut pour la classe est assignée aux nouveaux éléments.  
  
### <a name="remarks"></a>Remarques  
 Si la taille de la liste est inférieure à la taille demandée, `_Newsize`, des éléments sont ajoutés à la liste jusqu’à ce qu’elle atteigne la taille demandée.  
  
 Si la taille de la liste est supérieure à la taille demandée, les éléments les plus proches de la fin de la liste sont supprimés jusqu’à ce que celle-ci atteigne la taille `_Newsize`.  
  
 Si la taille actuelle de la liste est égale à la taille demandée, aucune action n'est effectuée.  
  
 [size](#list__size) reflète la taille actuelle de la liste.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_resize.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{   
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is 4  
The value of the last element is 40  
The size of c1 is now 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namelistreversea--listreverse"></a><a name="list__reverse"></a>  list::reverse  
 Inverse l'ordre dans lequel les éléments apparaissent dans une liste.  
  
``` 
void reverse();
```  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_reverse.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.reverse( );  
   cout << "Reversed c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
c1 = 10 20 30  
Reversed c1 = 30 20 10  
```  
  
##  <a name="a-namelistreverseiteratora--listreverseiterator"></a><a name="list__reverse_iterator"></a>  list::reverse_iterator  
 Type qui fournit un itérateur bidirectionnel pouvant lire ou modifier un élément d'une liste inversée.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarques  
 Un type `reverse_iterator` est utilisé pour itérer la liste dans l'ordre inverse.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [rbegin](#list__rbegin).  
  
##  <a name="a-namelistsizea--listsize"></a><a name="list__size"></a>  list::size  
 Retourne le nombre d'éléments d'une liste.  
  
``` 
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Longueur actuelle de la liste.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_size.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::size_type i;  
  
   c1.push_back( 5 );  
   i = c1.size( );  
   cout << "List length is " << i << "." << endl;  
  
   c1.push_back( 7 );  
   i = c1.size( );  
   cout << "List length is now " << i << "." << endl;  
}  
```  
  
```Output  
List length is 1.  
List length is now 2.  
```  
  
##  <a name="a-namelistsizetypea--listsizetype"></a><a name="list__size_type"></a>  list::size_type  
 Type qui compte le nombre d'éléments dans une liste.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [size](#list__size).  
  
##  <a name="a-namelistsorta--listsort"></a><a name="list__sort"></a>  list::sort  
 Réorganise les éléments d’une liste dans l’ordre croissant ou en fonction d’un autre ordre spécifié par l’utilisateur.  
  
``` 
void sort();

template <class Traits>  
void sort(Traits comp);
```  
  
### <a name="parameters"></a>Paramètres  
 ` comp`  
 Opérateur de comparaison utilisé pour classer les éléments consécutifs.  
  
### <a name="remarks"></a>Remarques  
 La première fonction membre trie les éléments dans l’ordre croissant par défaut.  
  
 La fonction de modèle membre trie les éléments en fonction de l’opération de comparaison spécifiée par l’utilisateur ` comp` de classe **Traits**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_sort.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 20 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
  
   cout << "Before sorting: c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.sort( );  
   cout << "After sorting c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.sort( greater<int>( ) );  
   cout << "After sorting with 'greater than' operation, c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
Before sorting: c1 = 20 10 30  
After sorting c1 = 10 20 30  
After sorting with 'greater than' operation, c1 = 30 20 10  
```  
  
##  <a name="a-namelistsplicea--listsplice"></a><a name="list__splice"></a>  list::splice  
 Supprime des éléments d'une liste source et les insère dans une liste de destination.  
  
```  
// insert the entire source list  
void splice(const_iterator Where, list<Type, Allocator>& Source);
void splice(const_iterator Where, list<Type, Allocator>&& Source); 

// insert one element of the source list  
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator Iter);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator Iter);
 
// insert a range of elements from the source list  
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator First, const_iterator Last);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator First, const_iterator Last);
```  
  
### <a name="parameters"></a>Paramètres  
 `Where`  
 Position dans la liste de destination avant laquelle l'insertion doit être effectuée.  
  
 `Source`  
 Liste source qui doit être insérée dans la liste de destination.  
  
 `Iter`  
 Élément à insérer à partir de la liste source.  
  
 `First`  
 Premier élément de la plage à insérer à partir de la liste source.  
  
 `Last`  
 Première position au-delà du dernier élément de la plage à insérer à partir de la liste source.  
  
### <a name="remarks"></a>Remarques  
 La première paire de fonctions membres insère tous les éléments de la liste source dans la liste de destination avant la position référencée par `Where` et supprime tous les éléments de la liste source. ( `&Source` ne doit pas être égal à `this`.)  
  
 La deuxième paire de fonctions membres insère l'élément référencé par `Iter` avant la position dans la liste de destination référencée par `Where` et supprime `Iter` de la liste source. (Si `Where == Iter || Where == ++Iter`, aucune modification ne se produit.)  
  
 La troisième paire de fonctions membres insère la plage désignée par [ `First`, `Last`) avant l’élément dans la liste de destination référencé par `Where`, et supprime cette plage d’éléments de la liste source. (Si `&Source == this`, la plage `[First, Last)` ne doit pas inclure l'élément vers lequel `Where` pointe.)  
  
 Si la méthode splice à plage insère `N` éléments et que `&Source != this`, un objet de classe [iterator](../standard-library/forward-list-class.md#forward_list__iterator) est incrémenté `N` fois.  
  
 Dans tous les cas, les itérateurs, pointeurs ou références qui désignent des éléments ajoutés restent valides et sont transférés vers le conteneur de destination.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_splice.cpp  
// compile with: /EHsc /W4  
#include <list>  
#include <iostream>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: ";  
  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    list<int> c1{10,11};  
    list<int> c2{20,21,22};  
    list<int> c3{30,31};  
    list<int> c4{40,41,42,43};  
  
    list<int>::iterator where_iter;  
    list<int>::iterator first_iter;  
    list<int>::iterator last_iter;  
  
    cout << "Beginning state of lists:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
    cout << "c3 = ";  
    print(c3);  
    cout << "c4 = ";  
    print(c4);  
  
    where_iter = c2.begin();  
    ++where_iter; // start at second element  
    c2.splice(where_iter, c1);  
    cout << "After splicing c1 into c2:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c3.begin();  
    c2.splice(where_iter, c3, first_iter);  
    cout << "After splicing the first element of c3 into c2:" << endl;  
    cout << "c3 = ";  
    print(c3);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c4.begin();  
    last_iter = c4.end();  
    // set up to get the middle elements  
    ++first_iter;  
    --last_iter;  
    c2.splice(where_iter, c4, first_iter, last_iter);  
    cout << "After splicing a range of c4 into c2:" << endl;  
    cout << "c4 = ";  
    print(c4);  
    cout << "c2 = ";  
    print(c2);  
}  
  
```  
  
```Output  
Beginning state of lists:c1 = 2 elements: (10) (11)c2 = 3 elements: (20) (21) (22)c3 = 2 elements: (30) (31)c4 = 4 elements: (40) (41) (42) (43)After splicing c1 into c2:c1 = 0 elements:c2 = 5 elements: (20) (10) (11) (21) (22)After splicing the first element of c3 into c2:c3 = 1 elements: (31)c2 = 6 elements: (20) (10) (11) (30) (21) (22)After splicing a range of c4 into c2:c4 = 2 elements: (40) (43)c2 = 8 elements: (20) (10) (11) (30) (41) (42) (21) (22)  
```  
  
##  <a name="a-namelistswapa--listswap"></a><a name="list__swap"></a>  list::swap  
 Échange les éléments de deux listes.  
  
``` 
void swap(list<Type, Allocator>& right);
friend void swap(list<Type, Allocator>& left, list<Type, Allocator>& right)  
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Liste qui fournit les éléments à échanger, ou liste dont les éléments doivent être échangés avec ceux de la liste ` left`.  
  
 ` left`  
 Liste dont les éléments doivent être échangés avec ceux de la liste ` right`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_swap.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1, c2, c3;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original list c1 is: 1 2 3  
After swapping with c2, list c1 is: 10 20  
After swapping with c3, list c1 is: 100  
```  
  
##  <a name="a-namelistuniquea--listunique"></a><a name="list__unique"></a>  list::unique  
 Supprime les doublons adjacents ou les éléments adjacents qui satisfont un autre prédicat binaire dans une liste.  
  
```  
void unique();

template <class BinaryPredicate>  
void unique(BinaryPredicate pred);
```  
  
### <a name="parameters"></a>Paramètres  
 ` pred`  
 Prédicat binaire utilisé pour comparer des éléments consécutifs.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction suppose que la liste est triée, pour que tous les éléments dupliqués soient adjacents. Les doublons qui ne sont pas adjacents ne sont pas supprimés.  
  
 La première fonction membre supprime chaque élément dont la valeur est égale à l'élément précédent.  
  
 La seconde fonction membre supprime chaque élément conforme à la fonction de prédicat ` pred` par comparaison à son élément précédent. Vous pouvez utiliser tous les objets de fonction binaire déclarés dans l’en-tête `<functional>` pour l’argument pred ou créer votre propre objet.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_unique.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter,c3_Iter;  
   not_equal_to<int> mypred;  
  
   c1.push_back( -10 );  
   c1.push_back( 10 );  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 20 );  
   c1.push_back( -10 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.unique( );  
   cout << "After removing successive duplicate elements, c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   list <int> c3 = c2;  
   c3.unique( mypred );  
   cout << "After removing successive unequal elements, c3 =";  
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
      cout << " " << *c3_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = -10 10 10 20 20 -10  
After removing successive duplicate elements, c2 = -10 10 20 -10  
After removing successive unequal elements, c3 = -10 -10  
```  
  
##  <a name="a-namelistvaluetypea--listvaluetype"></a><a name="list__value_type"></a>  list::value_type  
 Type qui représente le type de données stocké dans une liste.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Remarques  
 `value_type` est un synonyme du paramètre de modèle **Type**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// list_value_type.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<list>](../standard-library/list.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)

