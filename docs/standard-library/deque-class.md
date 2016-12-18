---
title: "deque, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.deque"
  - "deque"
  - "std::deque"
  - "deque/std::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "deque (classe), à propos de deque (classe)"
  - "deque (classe)"
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# deque, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Organise les éléments d'un type en un arrangement linéaire et, comme un vecteur, permet un accès aléatoire rapide à n'importe quel élément, ainsi que l'insertion et la suppression efficace à l'arrière du conteneur. Cependant, contrairement à un vecteur, la classe `deque` prend également en charge l'insertion et la suppression efficace à l'avant du conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```unstlib  
template <class Type,   
    class Allocator =allocator<Type>>  
class deque  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Type`  
 Type de données de l'élément à stocker dans la file d'attente à deux extrémités.  
  
 `Allocator`  
 Type qui représente l'objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire de la file d'attente à deux extrémités. Cet argument est facultatif et la valeur par défaut est **allocateur \< Type>***.*  
  
## <a name="remarks"></a>Notes  
 Le choix du type de conteneur doit être basé en général sur le type de la recherche et de l'insertion requis par l'application. [Vecteurs](vector%20Class.md) doit être le conteneur par défaut pour la gestion d’une séquence quand un accès aléatoire à n’importe quel élément est primordial et insertions ou les suppressions d’éléments sont seulement nécessaires à la fin d’une séquence. Les performances du conteneur de liste soient supérieures lorsque efficace insertions et suppressions (en temps constant) à n’importe quel emplacement dans la séquence est limité. Ces opérations au milieu de la séquence nécessitent des copies et des affectations d'éléments proportionnellement au nombre d'éléments de la séquence (délai linéaire).  
  
 La réallocation de la file d'attente à deux extrémités se produit quand une fonction membre doit insérer ou effacer des éléments de la séquence :  
  
-   Si un élément est inséré dans une séquence vide, ou si un élément est effacé pour laisser une séquence vide, puis itérateurs précédemment retourné par [commencer](#deque__begin) et [fin](#deque__end) deviennent non valides.  
  
-   Si un élément est inséré à la première position de la file d'attente à deux extrémités, tous les itérateurs, mais aucune des références, désignant les éléments existants deviennent non valides.  
  
-   Si un élément est inséré à la fin de la deque, [fin](#deque__end) et tous les itérateurs, mais aucune référence, qui désignent les éléments existants ne sont plus valides.  
  
-   Si un élément est effacé à l'avant de la file d'attente à deux extrémités, seul cet itérateur et les références à l'élément effacé deviennent non valides.  
  
-   Si le dernier élément est effacé de la fin de la file d'attente à deux extrémités, seul cet itérateur vers l'élément final et les références à l'élément effacé deviennent non valides.  
  
 Dans le cas contraire, l'insertion ou la suppression d'un élément invalide tous les itérateurs et toutes les références.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[deque](#deque__deque)|Construit un `deque.` plusieurs constructeurs permettent de paramétrer le contenu de la nouvelle `deque` de différentes façons : vide ; chargé avec un nombre spécifié d’éléments vides ; contenu déplacé ou copié à partir d’un autre `deque`; contenu copié ou déplacé à l’aide d’un itérateur ; et un seul élément est copié dans la `deque`` count` fois. Certains constructeurs permettent l'utilisation d'un `allocator` personnalisé pour créer des éléments.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#deque__allocator_type)|Type qui représente la classe `allocator` pour l'objet `deque`.|  
|[const_iterator](#deque__const_iterator)|Type qui fournit un itérateur à accès aléatoire qui peut accéder à et lire des éléments dans la `deque` en tant que `const`.|  
|[const_pointer](#deque__const_pointer)|Type qui fournit un pointeur vers un élément d'une `deque` en tant que `const.`.|  
|[const_reference](#deque__const_reference)|Type qui fournit une référence à un élément d'une  `deque` pour la lecture et d'autres opérations en tant que `const.`.|  
|[const_reverse_iterator](#deque__const_reverse_iterator)|Type qui fournit un itérateur à accès aléatoire qui peut accéder à et lire des éléments dans la `deque` en tant que `const`. La file d'attente à deux extrémités est affichée dans l'ordre inverse. Pour plus d’informations, consultez [reverse_iterator, classe](../standard-library/reverse-iterator-class.md)|  
|[difference_type](#deque__difference_type)|Type qui fournit la différence entre deux itérateurs à accès aléatoire qui référencent des éléments de la même `deque`.|  
|[itérateur](#deque__iterator)|Type qui fournit un itérateur à accès aléatoire qui peut lire ou modifier tout élément d'une `deque`.|  
|[pointeur](#deque__pointer)|Type qui fournit un pointeur vers un élément d'un objet `deque`.|  
|[référence](#deque__reference)|Type qui fournit une référence à un élément stocké dans un `deque`.|  
|[reverse_iterator](#deque__reverse_iterator)|Type qui fournit un itérateur à accès aléatoire qui peut lire ou modifier un élément d'une `deque`. La file d'attente à deux extrémités est affichée dans l'ordre inverse.|  
|[size_type](#deque__size_type)|Type qui compte le nombre d'éléments d'une `deque`.|  
|[Value_type](#deque__value_type)|Type qui représente le type de données stocké dans un `deque`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[attribuer](#deque__assign)|Efface les éléments d'une `deque` et copie une nouvelle séquence d'éléments vers la `deque` cible.|  
|[à](#deque__at)|Retourne une référence à l'élément à un emplacement spécifié dans la `deque`.|  
|[Précédent](#deque__back)|Retourne une référence au dernier élément de la `deque`.|  
|[commencer](#deque__begin)|Retourne un itérateur à accès aléatoire pointant vers le premier élément de la `deque`.|  
|[deque::cbegin](#deque__cbegin)|Retourne un itérateur const vers le premier élément de la `deque`.|  
|[deque::cend](#deque__cend)|Retourne un itérateur `const` à accès aléatoire qui pointe juste après la fin de la `deque`.|  
|[Effacer](#deque__clear)|Efface tous les éléments d'un `deque`.|  
|[deque::crbegin](#deque__crbegin)|Retourne un itérateur const à accès aléatoire pointant vers le premier élément d'une `deque` affichée en ordre inverse.|  
|[deque::crend](#deque__crend)|Retourne un itérateur const à accès aléatoire pointant vers le premier élément d'une `deque` affichée en ordre inverse.|  
|[deque::emplace](#deque__emplace)|Insère un élément construit sur place à la position spécifiée dans la `deque`.|  
|[deque::emplace_back](#deque__emplace_back)|Ajoute un élément construit sur place à la fin de la `deque`.|  
|[deque::emplace_front](#deque__emplace_front)|Ajoute un élément construit sur place au début de la `deque`.|  
|[vide](#deque__empty)|Retourne `true` si la `deque` ne contient pas d'élément, et `false` si elle contient un ou plusieurs éléments.|  
|[fin](#deque__end)|Retourne un itérateur à accès aléatoire qui pointe juste après la fin de la `deque`.|  
|[effacement](#deque__erase)|Supprime un élément ou une plage d'éléments aux positions spécifiées d'une `deque`.|  
|[premier plan](#deque__front)|Retourne une référence au premier élément d'une `deque`.|  
|[get_allocator](#deque__get_allocator)|Retourne une copie de l'objet `allocator` qui est utilisé pour construire le `deque`.|  
|[Insérer](#deque__insert)|Insère un élément, plusieurs éléments ou une plage d'éléments dans la `deque` à une position spécifiée.|  
|[max_size](#deque__max_size)|Retourne la longueur maximale possible de la `deque`.|  
|[pop_back](#deque__pop_back)|Efface l'élément à la fin de la `deque`.|  
|[pop_front](#deque__pop_front)|Efface l'élément au début de la `deque`.|  
|[push_back](#deque__push_back)|Ajoute un élément à la fin de la `deque`.|  
|[push_front](#deque__push_front)|Ajoute un élément au début de la `deque`.|  
|[rbegin](#deque__rbegin)|Retourne un itérateur à accès aléatoire vers le premier élément d'une `deque` inversée.|  
|[rend)](#deque__rend)|Retourne un itérateur qui pointe juste après le dernier élément d'une `deque` inversée.|  
|[redimensionner](#deque__resize)|Spécifie une nouvelle taille pour un objet `deque`.|  
|[deque::shrink_to_fit](#deque__shrink_to_fit)|Ignore la capacité excédentaire.|  
|[taille](#deque__size)|Retourne le nombre d'éléments d'un `deque`.|  
|[échange](#deque__swap)|Échange les éléments de deux `deque`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur &#91 ; &#93 ;](#deque__operator_at)|Retourne une référence à l'élément d'un objet `deque` à une position spécifiée.|  
|[deque::operator =](#deque__operator_eq)|Remplace les éléments de l'objet `deque` par une copie d'un autre objet `deque`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête**: \< deque>  
  
##  <a name="a-namedequeallocatortypea-dequeallocatortype"></a><a name="deque__allocator_type"></a>  deque::allocator_type  
 Type qui représente la classe d’allocateur pour l’objet deque.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Notes  
 **allocator_type** est un synonyme du paramètre de modèle **allocateur**.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [get_allocator](#deque__get_allocator).  
  
##  <a name="a-namedequeassigna-dequeassign"></a><a name="deque__assign"></a>  deque::Assign  
 Efface les éléments d’un deque et copie un nouvel ensemble d’éléments dans le deque cible.  
  
```  
template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);

void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>Paramètres  
 `First`  
 Position du premier élément dans la plage d’éléments à copier à partir de l’argument deque.  
  
 `Last`  
 Position du premier élément au-delà de la plage d’éléments à copier à partir de l’argument deque.  
  
 `Count`  
 Le nombre de copies d’un élément inséré dans le deque.  
  
 `Val`  
 La valeur de l’élément inséré dans le deque.  
  
 `IList`  
 Initializer_list inséré dans le deque.  
  
### <a name="remarks"></a>Notes  
 Une fois les éléments existants dans la cible deque sont effacés, `assign` insère une plage d’éléments spécifiée à partir de la deque d’origine ou de certains autres deque dans la cible deque, ou insère des copies d’un nouvel élément de la valeur spécifiée dans la cible deque.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_assign.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <initializer_list>  
  
int main()  
{  
    using namespace std;  
    deque <int> c1, c2;  
    deque <int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    deque<int> d1{ 1, 2, 3, 4 };  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    d1.assign(iList);  
  
    cout << "d1 = ";  
    for (int i : d1)  
        cout << i;  
    cout << endl;  
  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
}  
  
```  
  
```Output  
d1 = 5678c1 =102030c1 =5060c1 =4444444  
```  
  
##  <a name="a-namedequeata-dequeat"></a><a name="deque__at"></a>  deque::AT  
 Retourne une référence à l’élément à un emplacement spécifié dans le deque.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Pos`  
 L’indice (ou numéro de position) de l’élément à référencer dans le deque.  
  
### <a name="return-value"></a>Valeur de retour  
 Si `_Pos` est supérieure à la taille de la deque, **à** lève une exception.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour de **à** est affecté à un `const_reference`, l’objet deque ne peut pas être modifié. Si la valeur de retour de **à** est affecté à un **référence**, l’objet deque peut être modifié.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_at.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int& i = c1.at( 0 );  
   int& j = c1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequebacka-dequeback"></a><a name="deque__back"></a>  deque::back  
 Retourne une référence au dernier élément de la deque.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le dernier élément de la deque. Si le deque est vide, la valeur de retour est non définie.  
  
### <a name="remarks"></a>Notes  
 Si la valeur de retour de **retour** est affecté à un `const_reference`, l’objet deque ne peut pas être modifié. Si la valeur de retour de **retour** est affecté à un **référence**, l’objet deque peut être modifié.  
  
 Compilation avec _SECURE_SCL 1, une erreur d’exécution se produit si vous tentez d’accéder à un élément dans un deque vide.  Pour plus d'informations, voir [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```  
// deque_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
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
  
##  <a name="a-namedequebegina-dequebegin"></a><a name="deque__begin"></a>  deque::BEGIN  
 Retourne un itérateur qui traite le premier élément dans le deque.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur à accès aléatoire traite le premier élément dans le deque ou à l’emplacement suivant un deque vide.  
  
### <a name="remarks"></a>Notes  
 Si la valeur de retour de **commencer** est affecté à un `const_iterator`, l’objet deque ne peut pas être modifié. Si la valeur de retour de **commencer** est affecté à un **itérateur**, l’objet deque peut être modifié.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_begin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::const_iterator c1_cIter;  
  
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
  
##  <a name="a-namedequecbegina-dequecbegin"></a><a name="deque__cbegin"></a>  deque::cbegin  
 Retourne un itérateur `const` qui traite le premier élément d'une plage.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d'accès aléatoire `const` qui pointe vers le premier élément de la plage, ou vers l'emplacement situé juste après la fin d'une plage vide (pour une plage vide : `cbegin() == cend()`).  
  
### <a name="remarks"></a>Notes  
 Avec la valeur de retour `cbegin`, les éléments de la plage ne peuvent pas être modifiés.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `begin()` afin de garantir que la valeur de retour est `const_iterator`. En règle générale, il est utilisé conjointement avec la [automatique](../cpp/auto-cpp.md) Tapez le mot clé de déduction, comme illustré dans l’exemple suivant. Dans l’exemple, considérez `Container` soient un modifiables (non - `const`) conteneur de tout type qui prend en charge `begin()` et `cbegin()`.  
  
```cpp  
 
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namedequecenda-dequecend"></a><a name="deque__cend"></a>  deque::cend  
 Retourne un itérateur `const` qui traite l'emplacement situé immédiatement après le dernier élément d'une plage.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d'accès aléatoire qui pointe juste après la fin de la plage.  
  
### <a name="remarks"></a>Notes  
 `cend` est utilisé pour vérifier si un itérateur a dépassé la fin de la plage.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `end()` afin de garantir que la valeur de retour est `const_iterator`. En règle générale, il est utilisé conjointement avec la [automatique](../cpp/auto-cpp.md) Tapez le mot clé de déduction, comme illustré dans l’exemple suivant. Dans l’exemple, considérez `Container` soient un modifiables (non - `const`) conteneur de tout type qui prend en charge `end()` et `cend()`.  
  
```cpp  
 
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 La valeur retournée par `cend` ne doit pas être déréférencée.  
  
##  <a name="a-namedequecleara-dequeclear"></a><a name="deque__clear"></a>  deque::Clear  
 Efface tous les éléments d’un deque.  
  
```  
void clear();
```  
  
### <a name="example"></a>Exemple  
  
```  
// deque_clear.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the deque is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the deque is initially 3  
The size of the deque after clearing is 0  
```  
  
##  <a name="a-namedequeconstiteratora-dequeconstiterator"></a><a name="deque__const_iterator"></a>  deque::const_iterator  
 Type qui fournit un itérateur à accès aléatoire qui peut accéder et lire un **const** élément dans le deque.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Un type `const_iterator` ne peut pas être utilisé pour changer la valeur d'un élément.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [dans](#deque__back).  
  
##  <a name="a-namedequeconstpointera-dequeconstpointer"></a><a name="deque__const_pointer"></a>  deque::const_pointer  
 Fournit un pointeur vers un `const` élément dans une deque.  
  
```unstlib  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Un type `const_pointer` ne peut pas être utilisé pour changer la valeur d'un élément. Un [itérateur](#deque__iterator) est généralement utilisé pour accéder à un élément deque.  
  
##  <a name="a-namedequeconstreferencea-dequeconstreference"></a><a name="deque__const_reference"></a>  deque::const_reference  
 Type qui fournit une référence à un **const** élément stocké dans un deque pour lire et effectuer **const** operations.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Notes  
 Un type `const_reference` ne peut pas être utilisé pour changer la valeur d'un élément.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_const_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const deque <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequeconstreverseiteratora-dequeconstreverseiterator"></a><a name="deque__const_reverse_iterator"></a>  deque::const_reverse_iterator  
 Type qui fournit un itérateur à accès aléatoire capable de lire un **const** élément dans le deque.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Un type `const_reverse_iterator` ne peuvent pas modifier la valeur d’un élément et est utilisé pour itérer au sein du deque dans l’ordre inverse.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [rbegin](#deque__rbegin) pour obtenir un exemple montrant comment déclarer et utiliser un itérateur.  
  
##  <a name="a-namedequecrbegina-dequecrbegin"></a><a name="deque__crbegin"></a>  deque::crbegin  
 Retourne un itérateur const sur le premier élément dans un deque inversée.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur à accès aléatoire traite le premier élément dans une liste inversée inverse const [deque](../standard-library/deque-class.md) ou de traiter ce qui a été le dernier élément de la non inversé `deque`.  
  
### <a name="remarks"></a>Notes  
 Avec la valeur de retour `crbegin`, l'objet `deque` ne peut pas être changé.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_crbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator v1_Iter;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of deque is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed deque is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of deque is 1.  
The first element of the reversed deque is 2.  
```  
  
##  <a name="a-namedequecrenda-dequecrend"></a><a name="deque__crend"></a>  deque::crend  
 Retourne un itérateur const qui traite l’emplacement suivant le dernier élément d’un deque inversée.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur à accès aléatoire qui traite l’emplacement suivant le dernier élément dans une liste inversée inverse const [deque](../standard-library/deque-class.md) (l’emplacement ayant précédé le premier élément dans le deque non inversé).  
  
### <a name="remarks"></a>Notes  
 `crend` est utilisé avec un inversée `deque` comme [array::cend](../standard-library/array-class-stl.md#array__cend) est utilisé avec un `deque`.  
  
 Avec la valeur de retour de `crend` (convenablement décrémenté), la `deque` objet ne peut pas être modifié.  
  
 `crend` peut être utilisé pour tester si un itérateur inverse a atteint la fin de son deque.  
  
 La valeur retournée par `crend` ne doit pas être déréférencée.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_crend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namedequedequea-dequedeque"></a><a name="deque__deque"></a>  deque::deque  
 Construit un deque d’une taille spécifique ou contenant des éléments d’une valeur spécifique, ou avec un allocateur spécifique ou comme une copie de l’ensemble ou une partie de certaines autres deque.  
  
```  
deque();

explicit deque(
    const Allocator& Al);

explicit deque(
    size_type Count);

deque(
    size_type Count,  
    const Type& Val);

deque(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

deque(
    const deque& Right);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);

deque(
    initializer_list<value_type>  
IList,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Al`|Classe allocator à utiliser avec cet objet.|  
|`Count`|Le nombre d’éléments dans le deque construit.|  
|`Val`|La valeur des éléments dans le deque construit.|  
|`Right`|Le deque dont le deque construit doit être une copie.|  
|`First`|Position du premier élément dans la plage d'éléments à copier.|  
|`Last`|Position du premier élément suivant la fin de la plage d'éléments à copier.|  
|`IList`|Initializer_list doit être copié.|  
  
### <a name="remarks"></a>Notes  
 Tous les constructeurs stockent un objet allocateur ( `Al`) et initialiser le deque.  
  
 Les deux premiers constructeurs spécifient une deque initiale vide ; le second exemple spécifie également le type d’allocateur ( `_Al`) à utiliser.  
  
 Le troisième constructeur spécifie une répétition d’un nombre spécifié ( ` count`) des éléments de la valeur par défaut pour la classe `Type`.  
  
 Les quatrième et cinquième constructeurs spécifient une répétition des ( `Count`) éléments ayant la valeur ` val`.  
  
 Le sixième constructeur spécifie une copie de la deque `Right`.  
  
 Les septième et huitième constructeurs copient la plage `[First, Last)` d’un deque.  
  
 Le septième constructeur déplace le deque `Right`.  
  
 Le huitième constructeur copie le contenu d’initializer_list.  
  
 Aucun des constructeurs n'effectue de réallocations temporaires.  
  
### <a name="example"></a>Exemple  
  
```  
/ compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <forward_list>  
  
int main()  
{  
    using namespace std;  
  
    forward_list<int> f1{ 1, 2, 3, 4 };  
  
    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });  
  
    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1(3);  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2(5, 2);  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4(c2);  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5(c4.begin(), c4_Iter);  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for (int i : c1)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for (int i : c2)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for (int i : c3)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for (int i : c4)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for (int i : c5)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for (int i : c6)  
        cout << i << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7(move(c6));  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =";  
    for (int i : c7)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    for (int i : c9)  
        cout << i << " ";  
    cout << endl;  
  
    int x = 3;  
}  
// deque_deque.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
    using namespace std;  
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1( 3 );  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2( 5, 2 );  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3( 3, 1, c2.get_allocator( ) );  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4( c2 );  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin( );  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5( c4.begin( ), c4_Iter );  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin( );  
   c4_Iter++;  
   c4_Iter++;  
   c4_Iter++;  
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
        initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
        cout << *c1_Iter << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
        cout << *c2_Iter << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
        cout << *c3_Iter << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )  
        cout << *c4_Iter << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )  
        cout << *c5_Iter << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )  
        cout << *c6_Iter << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7( move(c6) );  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =" ;  
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )  
        cout << " " << *c7_Iter;  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    or (int i : c9)  
        cout << i << " ";  
    cout << endl;  
}  
```  
  
##  <a name="a-namedequedifferencetypea-dequedifferencetype"></a><a name="deque__difference_type"></a>  deque::difference_type  
 Type qui fournit la différence entre deux itérateurs qui font référence à des éléments dans le même deque.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Notes  
 Un `difference_type` peut également représenter le nombre d'éléments entre deux pointeurs.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <deque>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   deque <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
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
  
##  <a name="a-namedequeemplacea-dequeemplace"></a><a name="deque__emplace"></a>  deque::emplace  
 Insère un élément construit sur place dans le deque à la position spécifiée.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`_Where`|La position dans le [deque](../standard-library/deque-class.md) où le premier élément est inséré.|  
|` val`|Valeur de l'élément inséré dans le `deque`.|  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction retourne un itérateur qui pointe vers l’emplacement où le nouvel élément a été inséré dans le deque.  
  
### <a name="remarks"></a>Notes  
 Une opération d’insertion peut s’avérer coûteuse, consultez `deque` pour en savoir plus sur `deque` performances.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_emplace.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="a-namedequeemplacebacka-dequeemplaceback"></a><a name="deque__emplace_back"></a>  deque::emplace_back  
 Ajoute un élément construit sur place à la fin de la deque.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|L’élément ajouté à la fin de la [deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Exemple  
  
```  
// deque_emplace_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_back( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemplacefronta-dequeemplacefront"></a><a name="deque__emplace_front"></a>  deque::emplace_front  
 Ajoute un élément construit sur place à la fin de la deque.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|L’élément ajouté au début de la [deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Exemple  
  
```  
// deque_emplace_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_front( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemptya-dequeempty"></a><a name="deque__empty"></a>  deque::Empty  
 Teste si un deque est vide.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** Si le deque est vide ; **false** Si le deque n’est pas vide.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_empty.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The deque is empty." << endl;  
   else  
      cout << "The deque is not empty." << endl;  
}  
```  
  
```Output  
The deque is not empty.  
```  
  
##  <a name="a-namedequeenda-dequeend"></a><a name="deque__end"></a>  deque::end  
 Retourne un itérateur qui traite l’emplacement suivant le dernier élément d’un deque.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur à accès aléatoire qui traite l’emplacement suivant le dernier élément d’un deque. Si le deque est vide, puis deque::end == deque::begin.  
  
### <a name="remarks"></a>Notes  
 **fin** est utilisé pour déterminer si un itérateur a atteint la fin de son deque.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_end.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // deque <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The deque is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The deque is now: 10 400 30  
```  
  
##  <a name="a-namedequeerasea-dequeerase"></a><a name="deque__erase"></a>  deque::Erase  
 Supprime un élément ou une plage d’éléments dans un deque aux emplacements spécifiés.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Where`  
 Position de l’élément à supprimer de la deque.  
  
 ` first`  
 Position du premier élément supprimé le deque.  
  
 ` last`  
 Position juste après le dernier élément supprimé le deque.  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur à accès aléatoire qui désigne le premier élément restant après tous les éléments supprimés, ou un pointeur vers la fin de la deque si aucun élément n’existe.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur **Effacer**, consultez [deque::erase et deque::clear](../misc/deque-erase-and-deque-clear.md).  
  
 **Effacer** lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_erase.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial deque is: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the deque becomes:  ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, deque becomes: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The initial deque is: 10 20 30 40 50   
After erasing the first element, the deque becomes:  20 30 40 50   
After erasing all elements but the first, deque becomes: 20   
```  
  
##  <a name="a-namedequefronta-dequefront"></a><a name="deque__front"></a>  deque::front  
 Retourne une référence au premier élément dans un deque.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le deque est vide, la valeur de retour n’est pas défini.  
  
### <a name="remarks"></a>Notes  
 Si la valeur de retour de `front` est affecté à un `const_reference`, l’objet deque ne peut pas être modifié. Si la valeur de retour de `front` est affecté à un **référence**, l’objet deque peut être modifié.  
  
 Compilation avec _SECURE_SCL 1, une erreur d’exécution se produit si vous tentez d’accéder à un élément dans un deque vide.  Pour plus d'informations, voir [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```  
// deque_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.front( );  
   const int& ii = c1.front( );  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The second integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 11  
```  
  
##  <a name="a-namedequegetallocatora-dequegetallocator"></a><a name="deque__get_allocator"></a>  deque::get_allocator  
 Retourne une copie de l’objet allocateur utilisé pour construire le deque.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Allocateur utilisé par le deque.  
  
### <a name="remarks"></a>Notes  
 Les allocateurs de la classe deque spécifient comment la classe gère le stockage. Les allocateurs par défaut fournis avec les classes de conteneur STL sont suffisants pour la plupart des besoins en programmation. L'écriture et l'utilisation de votre propre classe d'allocateur font l'objet d'une rubrique avancée du langage C++.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_get_allocator.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   deque <int> c1;  
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   deque <int> c3( c1.get_allocator( ) );  
  
   deque <int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namedequeinserta-dequeinsert"></a><a name="deque__insert"></a>  deque::Insert  
 Insère un élément ou un nombre d’éléments ou une plage d’éléments dans le deque à la position spécifiée.  
  
```  
iterator insert(
    const_iterator Where,  
    const Type& Val);

iterator insert(
    const_iterator Where,  
    Type&& Val);

void insert(
    iterator Where,  
    size_type Count,  
    const Type& Val);

template <class InputIterator>  
void insert(
    iterator Where,  
    InputIterator First,  
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Where`|Position dans la cible deque où le premier élément est inséré.|  
|`Val`|La valeur de l’élément inséré dans le deque.|  
|`Count`|Le nombre d’éléments insérés dans le deque.|  
|`First`|La position du premier élément dans la plage d’éléments dans l’argument deque à copier.|  
|`Last`|Position du premier élément au-delà de la plage d’éléments dans l’argument deque à copier.|  
|`IList`|Initializer_list d’éléments à insérer.|  
  
### <a name="return-value"></a>Valeur de retour  
 Les deux premières fonctions insert retournent un itérateur qui pointe vers l’emplacement où le nouvel élément a été inséré dans le deque.  
  
### <a name="remarks"></a>Notes  
 Une opération d’insertion peut être coûteuse.  
  
##  <a name="a-namedequeiteratora-dequeiterator"></a><a name="deque__iterator"></a>  deque::iterator  
 Type qui fournit un itérateur à accès aléatoire pouvant lire ou modifier tout élément dans un deque.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Un type **itérateur** peut être utilisé pour modifier la valeur d’un élément.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [commencer](#deque__begin).  
  
##  <a name="a-namedequemaxsizea-dequemaxsize"></a><a name="deque__max_size"></a>  deque::max_size  
 Retourne la longueur maximale de la deque.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur maximale possible du deque.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_max_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "The maximum possible length of the deque is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namedequeoperatorata-dequeoperator"></a><a name="deque__operator_at"></a>  deque::operator]  
 Retourne une référence à l’élément deque à la position spécifiée.  
  
```  
reference operator[](size_type _Pos);

const_reference operator[](size_type _Pos) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Pos`  
 La position de l’élément deque à référencer.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’élément dont la position est spécifiée dans l’argument. Si la position spécifiée est supérieure à la taille de la deque, le résultat est indéfini.  
  
### <a name="remarks"></a>Notes  
 Si la valeur de retour de `operator[]` est affecté à un `const_reference`, l’objet deque ne peut pas être modifié. Si la valeur de retour de `operator[]` est affecté à un **référence**, l’objet deque peut être modifié.  
  
 Compilation avec _SECURE_SCL 1, une erreur d’exécution se produit si vous tentez d’accéder à un élément en dehors des limites de la deque.  Pour plus d'informations, voir [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```  
// deque_op_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   cout << "The first integer of c1 is " << c1[0] << endl;  
   int& i = c1[1];  
   cout << "The second integer of c1 is " << i << endl;  
  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 20  
```  
  
##  <a name="a-namedequeoperatoreqa-dequeoperator"></a><a name="deque__operator_eq"></a>  deque::operator =  
 Remplace les éléments de cette deque utilisant les éléments à partir d’un autre deque.  
  
```  
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` right`|Deque qui fournit le nouveau contenu.|  
  
### <a name="remarks"></a>Notes  
 Le remplacement de première copie des éléments dans cette deque de ` right`, la source de l’affectation. La deuxième substitution déplace des éléments vers cette deque de ` right`.  
  
 Éléments contenus dans cette deque avant l’exécution de l’opérateur sont supprimées.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_operator_as.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
using namespace std;  
  
typedef deque<int> MyDeque;  
  
template<typename MyDeque> struct S;  
  
template<typename MyDeque> struct S<MyDeque&> {  
  static void show( MyDeque& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
    cout << endl;  
  }  
};  
  
template<typename MyDeque> struct S<MyDeque&&> {  
  static void show( MyDeque&& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
cout << " via unnamed rvalue reference " << endl;  
  }  
};  
  
int main( )  
{  
   MyDeque d1, d2;  
  
   d1.push_back(10);  
   d1.push_back(20);  
   d1.push_back(30);  
   d1.push_back(40);  
   d1.push_back(50);  
  
   cout << "d1 = " ;  
   S<MyDeque&>::show( d1 );  
  
   d2 = d1;  
   cout << "d2 = ";  
   S<MyDeque&>::show( d2 );  
  
   cout << "     ";  
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );  
 }  
```  
  
##  <a name="a-namedequepointera-dequepointer"></a><a name="deque__pointer"></a>  deque::pointer  
 Fournit un pointeur vers un élément dans un [deque](../standard-library/deque-class.md).  
  
```unstlib  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Un type **pointeur** peut être utilisé pour modifier la valeur d’un élément. Un [itérateur](#deque__iterator) est généralement utilisé pour accéder à un élément deque.  
  
##  <a name="a-namedequepopbacka-dequepopback"></a><a name="deque__pop_back"></a>  deque::pop_back  
 Supprime l’élément à la fin de la deque.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Notes  
 Le dernier élément ne doit pas être vide. `pop_back` ne lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_pop_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the deque, the "  
      "last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the deque, the last element is: 1  
```  
  
##  <a name="a-namedequepopfronta-dequepopfront"></a><a name="deque__pop_front"></a>  deque::pop_front  
 Supprime l’élément au début de la deque.  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>Notes  
 Le premier élément ne doit pas être vide. `pop_front` ne lève jamais d’exception.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_pop_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the "  
      "deque, the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the deque, the first element is: 2  
```  
  
##  <a name="a-namedequepushbacka-dequepushback"></a><a name="deque__push_back"></a>  deque::push_back  
 Ajoute un élément à la fin de la deque.  
  
```  
void push_back(const Type& val);

void push_back(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|L’élément est ajouté à la fin de la deque.|  
  
### <a name="remarks"></a>Notes  
 Si une exception est levée, le deque reste inchangée et l’exception est levée de nouveau.  
  
##  <a name="a-namedequepushfronta-dequepushfront"></a><a name="deque__push_front"></a>  deque::push_front  
 Ajoute un élément au début de la deque.  
  
```  
    void push_front(const Type& val);

void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` val`|L’élément est ajouté au début de la deque.|  
  
### <a name="remarks"></a>Notes  
 Si une exception est levée, le deque reste inchangée et l’exception est levée de nouveau.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_push_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a deque of strings  
   deque <string> c2;  
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
  
##  <a name="a-namedequerbegina-dequerbegin"></a><a name="deque__rbegin"></a>  deque::rbegin  
 Retourne un itérateur au premier élément dans un deque inversée.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur à accès aléatoire inverse traite le premier élément dans un deque inversée ou de traiter ce qui a été le dernier élément dans le deque non inversé.  
  
### <a name="remarks"></a>Notes  
 `rbegin` est utilisé avec un deque inversée comme [commencer](#deque__begin) est utilisé avec un deque.  
  
 Si la valeur de retour de `rbegin` est affecté à un `const_reverse_iterator`, l’objet deque ne peut pas être modifié. Si la valeur de retour de `rbegin` est affecté à un `reverse_iterator`, l’objet deque peut être modifié.  
  
 `rbegin` peut être utilisé pour itérer un deque vers l’arrière.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_rbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error   
   // would have resulted in the line modifying an element   
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rbegin( );  
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;  
  
   cout << "The deque contains the elements: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << "in that order.";  
   cout << endl;  
  
   // rbegin can be used to iterate through a deque in reverse order  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  // This would have caused an error if a   
                    // const_reverse iterator had been declared as   
                    // noted above  
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
Last element in the deque is 30.  
The deque contains the elements: 10 20 30 in that order.  
The reversed deque is: 30 20 10   
Last element in deque is now 40.  
```  
  
##  <a name="a-namedequereferencea-dequereference"></a><a name="deque__reference"></a>  deque::Reference  
 Type qui fournit une référence à un élément stocké dans un deque.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Exemple  
  
```  
// deque_reference.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequerenda-dequerend"></a><a name="deque__rend"></a>  deque::rend  
 Retourne un itérateur qui traite l’emplacement suivant le dernier élément d’un deque inversée.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur à accès aléatoire inverse qui traite l’emplacement suivant le dernier élément dans un deque inversée (emplacement ayant précédé le premier élément dans le deque non inversé).  
  
### <a name="remarks"></a>Notes  
 `rend` est utilisé avec un deque inversée comme [fin](#deque__end) est utilisé avec un deque.  
  
 Si la valeur de retour de `rend` est affecté à un `const_reverse_iterator`, l’objet deque ne peut pas être modifié. Si la valeur de retour de `rend` est affecté à un `reverse_iterator`, l’objet deque peut être modifié.  
  
 `rend` peut être utilisé pour tester si un itérateur inverse a atteint la fin de son deque.  
  
 La valeur retournée par `rend` ne doit pas être déréférencée.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_rend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
   // If the following line had replaced the line above, an error  
   // would have resulted in the line modifying an element  
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --; // Decrementing a reverse iterator moves it forward   
                // in the deque (to point to the first element here)  
   cout << "The first element in the deque is: " << *c1_rIter << endl;  
  
   cout << "The deque is: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of   
   // the elements of a reversed deque  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--; // Decrementing the reverse iterator moves it backward   
               // in the reversed deque (to the last element here)  
 *c1_rIter = 40; // This modification of the last element would   
                   // have caused an error if a const_reverse   
                   // iterator had been declared (as noted above)  
   cout << "The modified reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The first element in the deque is: 10  
The deque is: 10 20 30   
The reversed deque is: 30 20 10   
The modified reversed deque is: 30 20 40   
```  
  
##  <a name="a-namedequeresizea-dequeresize"></a><a name="deque__resize"></a>  deque::Resize  
 Spécifie une nouvelle taille pour un deque.  
  
```  
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Newsize`  
 La nouvelle taille de la deque.  
  
 ` val`  
 La valeur des nouveaux éléments à ajouter à la deque si la nouvelle taille est plus grande que la taille d’origine. Si la valeur est omise, les nouveaux éléments sont affectés de la valeur par défaut pour la classe.  
  
### <a name="remarks"></a>Notes  
 Si la taille de la deque est inférieure à la taille demandée, `_Newsize`, éléments sont ajoutés à la deque jusqu'à ce qu’il atteigne la taille demandée.  
  
 Si la taille de la deque est supérieure à la taille demandée, les éléments le plus proche de la fin de la deque sont supprimés jusqu'à ce que le deque atteint la taille `_Newsize`.  
  
 Si la taille actuelle de la deque est identique à la taille demandée, aucune action n’est effectuée.  
  
 [taille](#deque__size) reflète la taille actuelle de la deque.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_resize.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{   
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is: 4  
The value of the last element is 40  
The size of c1 is now: 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namedequereverseiteratora-dequereverseiterator"></a><a name="deque__reverse_iterator"></a>  deque::reverse_iterator  
 Type qui fournit un itérateur à accès aléatoire pouvant lire ou modifier un élément d’un deque inversée.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Un type `reverse_iterator` est utilisé pour itérer au sein du deque.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de rbegin.  
  
##  <a name="a-namedequeshrinktofita-dequeshrinktofit"></a><a name="deque__shrink_to_fit"></a>  deque::shrink_to_fit  
 Ignore la capacité excédentaire.  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Notes  
 Il n’existe aucun moyen portable pour déterminer si `shrink_to_fit` réduit le stockage utilisé par un [deque](../standard-library/deque-class.md).  
  
### <a name="example"></a>Exemple  
  
```  
// deque_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   //deque <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
}  
```  
  
```Output  
Current size of v1 = 1  
Current size of v1 = 1  
```  
  
##  <a name="a-namedequesizea-dequesize"></a><a name="deque__size"></a>  deque::Size  
 Retourne le nombre d’éléments dans le deque.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur actuelle de la deque.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   c1.push_back( 1 );  
   i = c1.size( );  
   cout << "The deque length is " << i << "." << endl;  
  
   c1.push_back( 2 );  
   i = c1.size( );  
   cout << "The deque length is now " << i << "." << endl;  
}  
```  
  
```Output  
The deque length is 1.  
The deque length is now 2.  
```  
  
##  <a name="a-namedequesizetypea-dequesizetype"></a><a name="deque__size_type"></a>  deque::size_type  
 Type qui compte le nombre d’éléments dans un deque.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [taille](#deque__size).  
  
##  <a name="a-namedequeswapa-dequeswap"></a><a name="deque__swap"></a>  deque::swap  
 Échange les éléments de deux classes deque.  
  
```  
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>  
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Le deque qui fournit les éléments à permuter, ou le deque dont les éléments doivent être échangés avec ceux de la deque ` left`.  
  
 ` left`  
 Un deque dont les éléments doivent être échangés avec ceux de la deque ` right`.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_swap.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2, c3;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap<>(c1, c2);  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original deque c1 is: 1 2 3  
After swapping with c2, deque c1 is: 10 20  
After swapping with c3, deque c1 is: 100  
After swapping with c2, deque c1 is: 1 2 3  
```  
  
##  <a name="a-namedequevaluetypea-dequevaluetype"></a><a name="deque__value_type"></a>  deque::Value_type  
 Type qui représente le type de données stocké dans un deque.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Notes  
 `value_type` est un synonyme du paramètre de modèle **Type**.  
  
### <a name="example"></a>Exemple  
  
```  
// deque_value_type.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   deque<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

