---
title: valarray, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::valarray
- valarray/std::valarray::value_type
- valarray/std::valarray::apply
- valarray/std::valarray::cshift
- valarray/std::valarray::free
- valarray/std::valarray::max
- valarray/std::valarray::min
- valarray/std::valarray::resize
- valarray/std::valarray::shift
- valarray/std::valarray::size
- valarray/std::valarray::sum
- valarray/std::valarray::swap
dev_langs:
- C++
helpviewer_keywords:
- std::valarray [C++]
- std::valarray [C++], value_type
- std::valarray [C++], apply
- std::valarray [C++], cshift
- std::valarray [C++], free
- std::valarray [C++], max
- std::valarray [C++], min
- std::valarray [C++], resize
- std::valarray [C++], shift
- std::valarray [C++], size
- std::valarray [C++], sum
- std::valarray [C++], swap
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7b0c0499b9dfbaf3cb1f19eba16fc684a229839
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="valarray-class"></a>valarray, classe

La classe de modèle décrit un objet qui contrôle une séquence d'éléments de type **Type** qui sont stockés sous forme de tableau, conçu pour effectuer des opérations mathématiques très rapides et optimisé pour les performances de calcul.

## <a name="remarks"></a>Notes

La classe est une représentation du concept mathématique d'un ensemble ordonné de valeurs, et les éléments sont numérotés séquentiellement à partir de zéro. La classe est décrite comme un quasi conteneur, car elle prend en charge une partie seulement des capacités prises en charge par les conteneurs de séquences purs, comme [vector](../standard-library/vector-class.md). Elle diffère de la classe de modèle vector sur deux points importants :

- Elle définit de nombreuses opérations arithmétiques entre les éléments correspondants d’objets **valarray\<Type>** du même type et de même longueur, comme *xarr* = cos(*yarr*) + sin(*zarr*).

- Elle définit différents moyens intéressants d’indicer un objet **valarray\<Type>**, en surchargeant [operator&#91;&#93;](#op_at).

Un objet de classe **Type** :

- a un constructeur public par défaut, un destructeur, un constructeur de copie et un opérateur d'affectation, avec un comportement conventionnel.

- définit selon les besoins les opérateurs arithmétiques et les fonctions mathématiques qui sont définies pour les types à virgule flottante, avec un comportement conventionnel.

En particulier, aucune différence même minime ne peut exister entre la construction de copie et la construction par défaut suivie de l'affectation. Aucune des opérations sur les objets de la classe **Type** ne peut lever des exceptions.

### <a name="constructors"></a>Constructeurs

|Constructeur|Description|
|-|-|
|[valarray](#valarray)|Construit un `valarray` de taille spécifique ou avec des éléments d'une valeur spécifique, ou comme copie d'un autre `valarray` ou comme sous-ensemble d'un autre `valarray`.|

### <a name="typedefs"></a>Typedef

|Nom de type|Description|
|-|-|
|[value_type](#value_type)|Type qui représente le type des éléments stockés dans un `valarray`.|

### <a name="member-functions"></a>Fonctions membres

|Fonction membre|Description|
|-|-|
|[apply](#apply)|Applique une fonction spécifiée à chaque élément d'un `valarray`.|
|[cshift](#cshift)|Déplace de façon cyclique tous les éléments d'un `valarray` d'un nombre spécifié de positions.|
|[free](#free)|Libère la mémoire utilisée par le `valarray`.|
|[max](#max)|Recherche l'élément le plus grand dans un `valarray`.|
|[min](#min)|Recherche l'élément le plus petit dans un `valarray`.|
|[resize](#resize)|Change le nombre d'éléments d'un `valarray` pour un nouveau nombre spécifié, en ajoutant ou en supprimant des éléments selon les besoins.|
|[shift](#shift)|Déplace tous les éléments d'un `valarray` d'un nombre spécifié de positions.|
|[size](#size)|Trouve le nombre d'éléments d'un `valarray`.|
|[sum](#sum)|Détermine la somme de tous les éléments d'un `valarray` d'une longueur différente de zéro.|
|[swap](#swap)||

### <a name="operators"></a>Opérateurs

|Opérateur|Description|
|-|-|
|[operator!](#op_not)|Un opérateur unaire qui obtient les valeurs `NOT` logiques de chaque élément d'un `valarray`.|
|[operator%=](#op_mod_eq)|Obtient le reste de la division (élément par élément) des éléments d'un tableau par un `valarray` spécifié ou par une valeur du type d'élément.|
|[operator&=](#op_amp_eq)|Obtient le résultat d'une opération `AND` au niveau du bit des éléments d'un tableau avec les éléments correspondants d'un `valarray` spécifié ou avec une valeur du type d'élément.|
|[operator>>=](#op_gt_gt_eq)|Décale vers la droite les bits pour chaque élément d'un opérande `valarray` d'un nombre spécifié de positions ou d'une quantité élément par élément spécifiée par un second `valarray`.|
|[operator<<=](#op_lt_lt_eq)|Décale vers la gauche les bits pour chaque élément d'un opérande  `valarray` d'un nombre spécifié de positions ou d'une quantité élément par élément spécifiée par un second `valarray`.|
|[operator*=](#op_star_eq)|Multiplie les éléments d'un `valarray` spécifié ou une valeur du type d'élément, élément par élément, avec un `valarray` opérande.|
|[operator+](#op_add)|Un opérateur unaire qui applique un plus à chaque élément d'un `valarray`.|
|[operator+=](#op_add_eq)|Ajoute les éléments d'un `valarray` spécifié ou une valeur du type d'élément, élément par élément, à un `valarray` opérande.|
|[operator-](#operator-)|Un opérateur unaire qui applique un moins à chaque élément d'un `valarray`.|
|[operator-=](#operator-_eq)|Soustrait les éléments d'un `valarray` spécifié ou une valeur du type d'élément, élément par élément, d'un `valarray` opérande.|
|[operator/=](#op_div_eq)|Divise un `valarray` opérande, élément par élément, par les éléments d'un `valarray` spécifié ou par une valeur du type d'élément.|
|[operator=](#op_eq)|Affecte des éléments à un `valarray` dont les valeurs sont spécifiées directement ou comme une partie d'un autre `valarray`, ou par un `slice_array`, `gslice_array`, `mask_array` ou `indirect_array`.|
|[operator&#91;&#93;](#op_at)|Retourne une référence à un élément ou sa valeur à l'index spécifié, ou un sous-ensemble spécifié.|
|[operator^=](#op_xor_eq)|Obtient l’opérateur or exclusif logique au niveau des éléments (`XOR`) d’un tableau avec un valarray spécifié ou une valeur du type d’élément.|
|[operator&#124;=](#op_or_eq)|Obtient le résultat d'une opération `OR` au niveau du bit des éléments d'un tableau avec les éléments correspondants d'un `valarray` spécifié ou avec une valeur du type d'élément.|
|[operator~](#op_dtor)|Un opérateur unaire qui obtient les valeurs `NOT` au niveau du bit de chaque élément d'un `valarray`.|

## <a name="requirements"></a>Spécifications

**En-tête :** \<valarray>

**Espace de noms :** std

## <a name="apply"></a>  valarray::apply

Applique une fonction spécifiée à chaque élément d’un valarray.

```cpp
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```

### <a name="parameters"></a>Paramètres

*_Func(type)* l’objet de fonction à appliquer à chaque élément du valarray d’opérandes.

*_Func(const type&)* l’objet de fonction pour const à appliquer à chaque élément du valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments ont eu `_Func` appliqué élément par élément aux éléments du valarray d’opérandes.

### <a name="remarks"></a>Notes

La fonction membre retourne un objet de classe [valarray](../standard-library/valarray-class.md)**\<Type>**, de longueur [size](#size), dont chaque élément `I` est **func**(( **\*this**)[ `I`]).

### <a name="example"></a>Exemple

```cpp
// valarray_apply.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

using namespace std;

int __cdecl MyApplyFunc( int n )
{
   return n*2;
}

int main( int argc, char* argv[] )
{
   valarray<int> vaR(10), vaApplied(10);
   int i;

   for ( i = 0; i < 10; i += 3 )
      vaR[i] = i;

   for ( i = 1; i < 10; i += 3 )
      vaR[i] = 0;

   for ( i = 2; i < 10; i += 3 )
      vaR[i] = -i;

   cout << "The initial Right valarray is: (";
   for   ( i=0; i < 10; ++i )
      cout << " " << vaR[i];
   cout << " )" << endl;

   vaApplied = vaR.apply( MyApplyFunc );

   cout << "The element-by-element result of "
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";
   for ( i = 0; i < 10; ++i )
      cout << " " << vaApplied[i];
   cout << " )" << endl;
}
\* Output:
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )
The element-by-element result of applying MyApplyFunc to vaR is the
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )
*\
```

## <a name="cshift"></a>  valarray::cshift

Décale de façon cyclique tous les éléments dans un valarray d’un nombre spécifié d’emplacements.

```cpp
valarray<Type> cshift(int count) const;
```

### <a name="parameters"></a>Paramètres

`count` Le nombre de décimales que les éléments doivent être décalés vers l’avant.

### <a name="return-value"></a>Valeur de retour

Un nouveau valarray dans lequel tous les éléments ont été déplacés de `count` emplacements de façon cyclique vers l’avant du valarray, vers la gauche par rapport à leurs positions dans le valarray d’opérandes.

### <a name="remarks"></a>Notes

Une valeur positive de `count` décale les éléments de façon cyclique vers la gauche de `count` emplacements.

Une valeur négative de `count` décale les éléments de façon cyclique vers la droite de `count` emplacements.

### <a name="example"></a>Exemple

```cpp
// valarray_cshift.cpp
// compile with: /EHsc

#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    valarray<int> va1(10), va2(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;
    for (i = 0; i < 10; i+=1)
        va2[i] = 10 - i;

    cout << "The operand valarray va1 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    // A positive parameter shifts elements right
    va1 = va1.cshift(4);
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    cout << "The operand valarray va2 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;

    // A negative parameter shifts elements left
    va2 = va2.cshift(-4);
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;
}
\* Output:
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)
The cyclically shifted valarray va1 is:
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)
The cyclically shifted valarray va2 is:
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)
*\
```

## <a name="free"></a>  valarray::free

Libère la mémoire utilisée par le valarray.

```cpp
void free();
```

### <a name="remarks"></a>Notes

Cette fonction non standard est équivalente à l’attribution d’un valarray vide. Par exemple :

```cpp
valarray<T> v;
v = valarray<T>();

// equivalent to v.free()
```

## <a name="max"></a>  valarray::max

Recherche l’élément le plus grand dans un valarray.

```cpp
Type max() const;
```

### <a name="return-value"></a>Valeur de retour

La valeur maximale des éléments dans le valarray d’opérandes.

### <a name="remarks"></a>Notes

La fonction membre compare les valeurs en appliquant l’opérateur **operator\<** ou **operator>** entre les paires d’éléments de classe **Type**, pour lesquels les opérateurs doivent être fournis pour l’élément **Type**.

### <a name="example"></a>Exemple

```cpp
// valarray_max.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MaxValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i - 1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  10 - i;

   cout << "The operand valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MaxValue = vaR.max (  );
   cout << "The largest element in the valarray is: "
        << MaxValue  << "." << endl;
}
\* Output:
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).
The largest element in the valarray is: 13.
*\
```

## <a name="min"></a>  valarray::min

Recherche l’élément le plus petit dans un valarray.

```cpp
Type min() const;
```

### <a name="return-value"></a>Valeur de retour

La valeur minimale des éléments dans le valarray d’opérandes.

### <a name="remarks"></a>Notes

La fonction membre compare les valeurs en appliquant l’opérateur **operator\<** ou **operator>** entre les paires d’éléments de classe **Type**, pour lesquels les opérateurs doivent être fournis pour l’élément **Type**.

### <a name="example"></a>Exemple

```cpp
// valarray_min.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MinValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  5 - i;

   cout << "The operand valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MinValue = vaR.min ( );
   cout << "The smallest element in the valarray is: "
        << MinValue  << "." << endl;
}
\* Output:
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).
The smallest element in the valarray is: -9.
*\
```

## <a name="op_not"></a>  valarray::operator!

Opérateur unaire qui obtient les valeurs **NOT** logiques de chaque élément d’un valarray.

```cpp
valarray<bool> operator!() const;
```

### <a name="return-value"></a>Valeur de retour

Valarray de valeurs booléennes qui sont la négation des valeurs d’élément du valarray d’opérandes.

### <a name="remarks"></a>Notes

L’opération logique **NOT** inverse les éléments, car elle convertit tous les zéros en uns et considère toutes les valeurs différentes de zéro comme des uns et les convertit en zéros. Le valarray retourné de valeurs booléennes est de la même taille que le valarray d’opérandes.

Il existe également une opération de bits **NOT**[valarray::operator~](#op_dtor) qui inverse au niveau des bits individuels dans la représentation binaire des éléments `char` et `int` d’un valarray.

### <a name="example"></a>Exemple

```cpp
// valarray_op_lognot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<bool> vaNOT ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaNOT = !vaL;
   cout << "The element-by-element result of "
        << "the logical NOT operator! is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The element-by-element result of the logical NOT operator! is the
 valarray: ( 1 1 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_mod_eq"></a>  valarray::operator%=

Obtient le reste de la division (élément par élément) des éléments d’un tableau par un valarray spécifié ou par une valeur du type d’élément.

```cpp
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui consiste à diviser, élément par élément, le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont le reste de la division, élément par élément, du valarray d’opérandes par `right`

### <a name="example"></a>Exemple

```cpp
// valarray_class_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL %= vaR;
   cout << "The remainders from the element-by-element "
        << "division is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is: ( 53 -67 53 -67 53 -67 ).
The initial  right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
 valarray: ( 0 -3 4 -7 1 -3 ).
*\
```

## <a name="and_eq"></a>  valarray::operator&amp;=

Obtient le résultat de l’opération de bits **AND** des éléments d’un tableau avec les éléments correspondants dans un valarray spécifié ou avec une valeur du type d’élément.

```cpp
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui doit être combiné, élément par élément, par la logique **et** avec le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont le résultat de l’opération logique au niveau des éléments **AND** du valarray d’opérandes par `right`

### <a name="remarks"></a>Notes

Une opération de bits peut uniquement servir à manipuler des bits dans les types de données `char` et `int`, et leurs variantes, et non pas sur des types de données plus complexes **float**, **double**, **longdouble**, `void`, `bool` ou autres.

L’opérateur de bits AND a la même table de vérité que l’opérateur logique **AND**, mais il s’applique au type de données au niveau des bits individuels. Étant donné les bits *b*1 et *b*2, *b*1 **AND** *b*2 a la valeur **true** si les deux bits ont la valeur true ; ou **false** si au moins un des bits a la valeur false.

### <a name="example"></a>Exemple

```cpp
// valarray_class_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL &= vaR;
   cout << "The element-by-element result of "
        << "the logical AND operator&= is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&= is the
 valarray: ( 0 0 0 2 0 4 0 6 0 8 ).
*\
```

## <a name="op_gt_gt_eq"></a>  valarray::operator&gt;&gt;=

Décale vers la droite les bits de chaque élément d’un opérande de valarray d’un nombre spécifié de positions ou d’une quantité d’éléments spécifiée par un deuxième valarray.

```cpp
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` La valeur qui indique la quantité de décalage vers la droite ou valarray dont les éléments indiquent la quantité d’éléments de décalage vers la droite.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments ont été décalés vers la droite de la quantité spécifiée dans `right`.

### <a name="remarks"></a>Notes

Les signes des nombres signés sont préservés.

### <a name="example"></a>Exemple

```cpp
// valarray_class_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL >>= vaR;
   cout << "The element-by-element result of "
        << "the right shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*\
```

## <a name="op_lt_lt_eq"></a>  valarray::operator&lt;&lt;=

Décale vers la gauche les bits de chaque élément d’un opérande de valarray d’un nombre spécifié de positions ou d’une quantité d’éléments spécifiée par un deuxième valarray.

```cpp
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` La valeur qui indique la quantité de décalage vers la gauche ou valarray dont les éléments indiquent la quantité d’éléments de décalage vers la gauche.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments ont été décalés vers la gauche de la quantité spécifiée dans `right`.

### <a name="remarks"></a>Notes

Les signes des nombres signés sont préservés.

### <a name="example"></a>Exemple

```cpp
// valarray_class_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL <<= vaR;
   cout << "The element-by-element result of "
        << "the left shift\n on the operand array is the valarray:\n ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift
 on the operand array is the valarray:
 ( 1 -2 4 -8 16 -32 64 -128 ).
*\
```

## <a name="op_star_eq"></a>  valarray::operator*=

Multiplie les éléments d’un valarray spécifié ou une valeur du type d’élément, élément par élément, avec un valarray d’opérandes.

```cpp
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui consiste à multiplier, élément par élément, le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont le produit d’éléments du valarray d’opérandes et `right`.

### <a name="example"></a>Exemple

```cpp
// valarray_op_emult.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL *= vaR;
   cout << "The element-by-element result of "
        << "the multiplication is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*\
```

## <a name="op_add"></a>  valarray::operator+

Un opérateur unaire qui applique un plus à chaque élément d’un valarray.

```cpp
valarray<Type> operator+() const;
```

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont ajoutés à ceux du tableau d’opérandes.

### <a name="example"></a>Exemple

```cpp
// valarray_op_eplus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaPLUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaPLUS = +vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaPLUS [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
 valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
*\
```

## <a name="op_add_eq"></a>  valarray::operator+=

Ajoute les éléments d’un valarray spécifié ou une valeur du type d’élément, élément par élément, à un valarray d’opérandes.

```cpp
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui doit être ajouté, élément par élément, dans le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont la somme de la valarray d’opérandes et `right`.

### <a name="example"></a>Exemple

```cpp
// valarray_op_eadd.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL += vaR;
   cout << "The element-by-element result of "
        << "the sum is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
 valarray: ( 2 0 4 2 6 4 8 6 ).
*\
```

## <a name="valarray__operator-"></a>  valarray::operator-

Un opérateur unaire qui applique un moins à chaque élément dans un valarray.

```cpp
valarray<Type> operator-() const;
```

### <a name="return-value"></a>Valeur de retour

Un valarray d’éléments auxquels sont soustraits ceux du tableau d’opérandes.

### <a name="example"></a>Exemple

```cpp
// valarray_op_eminus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaMINUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaMINUS = -vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaMINUS [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
 valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).
*\
```

## <a name="valarray__operator-_eq"></a>  valarray::operator-=

Soustrait les éléments d’un valarray spécifié ou une valeur du type d’élément, élément par élément, à un valarray d’opérandes.

```cpp
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui doit être soustraite, élément par élément, le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont la différence du valarray d’opérandes et `right`.

### <a name="example"></a>Exemple

```cpp
// valarray_op_esub.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL -= vaR;
   cout << "The element-by-element result of "
        << "the difference is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*\
```

## <a name="op_div_eq"></a>  valarray::operator/=

Divise un valarray d’opérandes, élément par élément, par les éléments d’un valarray spécifié ou une valeur du type d’élément.

```cpp
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui doit être divisée, élément par élément, le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont le quotient de la valarray d’opérandes divisé par `right`.

### <a name="example"></a>Exemple

```cpp
// valarray_op_ediv.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL /= vaR;
   cout << "The element-by-element result of "
        << "the quotient is the\n valarray: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
 valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*\
```

## <a name="op_eq"></a>  valarray::operator=

Affecte des éléments à un valarray dont les valeurs sont spécifiées soit directement, soit dans le cadre d’un autre valarray ou par un slice_array, gslice_array, mask_array ou indirect_array.

```cpp
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray à copier dans le valarray d’opérandes.

`val` Valeur à affecter aux éléments du valarray d’opérandes.

`_Slicearray` Slice_array à copier dans le valarray d’opérandes.

`_Gslicearray` Gslice_array à copier dans le valarray d’opérandes.

`_Maskarray` Mask_array à copier dans le valarray d’opérandes.

`_Indarray` Indirect_array à copier dans le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Le premier opérateur membre remplace la séquence contrôlée par une copie de la séquence contrôlée par `right`.

Le deuxième opérateur membre est le même que le premier, mais avec un [déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).

Le troisième opérateur membre remplace chaque élément de la séquence contrôlée par une copie de `val`.

Les autres opérateurs membre remplacent les éléments de la séquence contrôlée sélectionnés par leurs arguments, qui sont générés uniquement par l’opérateur [operator&#91;&#93;](#op_at).

Si la valeur d’un membre dans la séquence contrôlée de remplacement dépend d’un membre dans la séquence contrôlée initiale, le résultat est indéfini.

### <a name="remarks"></a>Notes

Si la longueur de la séquence contrôlée change, le résultat est généralement non défini. Dans cette implémentation, toutefois, l’effet est simplement d’invalider tous les pointeurs ou références aux éléments dans la séquence contrôlée.

### <a name="example"></a>Exemple

```cpp
// valarray_op_assign.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va [ i ] = i;
   for ( i = 0 ; i < 10 ; i+=1 )
      vaR [ i ] = 10 -  i;

   cout << "The operand valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   cout << "The operand valarray vaR is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << vaR [ i ];
   cout << endl;

   // Assigning vaR to va with the first member functon
   va = vaR;
   cout << "The reassigned valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   // Assigning elements of value 10 to va
   // with the second member functon
   va = 10;
   cout << "The reassigned valarray va is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << va [ i ];
   cout << endl;
}
\* Output:
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10
*\
```

## <a name="op_at"></a>  valarray::operator[]

Retourne une référence à un élément ou sa valeur à l'index spécifié, ou un sous-ensemble spécifié.

```cpp
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;


valarray<Type> operator[](slice _Slice) const;


valarray<Type> operator[](const gslice& _Gslicearray) const;


valarray<Type> operator[](const valarray<bool>& _Boolarray) const;


valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```

### <a name="parameters"></a>Paramètres

`_Off` L’index de l’élément à assigner une valeur.

`_Slicearray` Un slice_array d’un valarray qui spécifie un sous-ensemble sélectionné ou retournée à un nouveau valarray.

`_Gslicearray` Un gslice_array d’un valarray qui spécifie un sous-ensemble sélectionné ou retournée à un nouveau valarray.

*_Boolarray* un bool_array d’un valarray qui spécifie un sous-ensemble sélectionné ou retournée à un nouveau valarray.

`_Indarray` Un indirect_array d’un valarray qui spécifie un sous-ensemble sélectionné ou retournée à un nouveau valarray.

### <a name="return-value"></a>Valeur de retour

Une référence à un élément ou sa valeur à l’index spécifié, ou un sous-ensemble spécifié.

### <a name="remarks"></a>Notes

L’opérateur de membre est surchargée pour fournir plusieurs méthodes pour sélectionner des éléments parmi celles contrôlé par les séquences *\****cela**. Le premier groupe de cinq opérateurs membres fonctionnent conjointement avec différentes surcharges de l’opérateur [operator=](#op_eq) (et d’autres opérateurs d’assignation) pour permettre le remplacement sélectif (découpage) de la séquence contrôlée. Les éléments sélectionnés doivent exister.

En cas de compilation avec [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) défini sur 1 ou 2, une erreur d’exécution se produit si vous essayez d’accéder à un élément en dehors des limites du valarray.  Pour plus d’informations, voir [Itérateurs vérifiés](../standard-library/checked-iterators.md).

### <a name="example"></a>Exemple

Consultez les exemples de [slice::slice](../standard-library/slice-class.md#slice) et [gslice::gslice](../standard-library/gslice-class.md#gslice) qui illustrent comment déclarer et utiliser l’opérateur.

## <a name="op_xor_eq"></a>  valarray::operator^=

Obtient l’opérateur ou exclusif logique au niveau des éléments (**XOR**) d’un tableau avec un valarray spécifié ou une valeur du type d’élément.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui doit être combiné, élément par élément, par l’exclusif logique **XOR** avec le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont l’élément par élément, exclusif logique **XOR** du valarray d’opérandes et `right`.

### <a name="remarks"></a>Notes

Ou exclusif logique, connu sous le nom **XOR**, a la sémantique suivante : étant donnés les éléments *e*1 et *e*2, *e*1 **XOR** *e*2 a la valeur **true** si exactement un des éléments a la valeur true ; **false** si les deux éléments ont la valeur false ou si les deux éléments ont la valeur true.

### <a name="example"></a>Exemple

```cpp
// valarray_op_exor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL ^= vaR;
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^= is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^= is the
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*\
```

## <a name="op_or_eq"></a>  valarray::operator&#124;=

Obtient le résultat de l’opération de bits `OR` des éléments d’un tableau avec les éléments correspondants dans un valarray spécifié ou avec une valeur du type d’élément.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Paramètres

`right` Le valarray ou la valeur d’un type d’élément identique à celle du valarray d’opérandes qui doit être combiné, élément par élément, par l’opérateur de bits `OR` avec le valarray d’opérandes.

### <a name="return-value"></a>Valeur de retour

Un valarray dont les éléments sont l’élément par élément au niveau du bit `OR` du valarray d’opérandes en `right`.

### <a name="remarks"></a>Notes

Une opération de bits peut uniquement servir à manipuler des bits dans les types de données `char` et `int`, et leurs variantes, et non pas sur des types de données plus complexes **float**, **double**, **longdouble**, `void`, `bool` ou autres.

L’opérateur de bits `OR` a la même table de vérité que l’opérateur `OR` logique, mais il s’applique au type de données au niveau des bits individuels. Étant donnés les bits *b*1 et *b*2, *b*1 `OR` *b*2 a la valeur **true** si au moins un des bits a la valeur true ; **false** si les deux bits ont la valeur false.

### <a name="example"></a>Exemple

```cpp
// valarray_class_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial operand valarray is:\n ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is:\n ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL |= vaR;
   cout << "The element-by-element result of "
        << "the logical OR\n operator|= is the valarray:\n ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial operand valarray is:
 ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is:
 ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the logical OR
 operator|= is the valarray:
 ( 1 0 1 3 3 4 7 6 7 9 ).
*\
```

## <a name="op_dtor"></a>  valarray::operator~

Opérateur unaire qui obtient les valeurs **NOT** au niveau du bit de chaque élément d’un valarray.

```cpp
valarray<Type> operator~() const;
```

### <a name="return-value"></a>Valeur de retour

Valarray de valeurs booléennes qui sont le résultat de l’opération **NOT** au niveau du bit des valeurs d’élément du valarray d’opérandes.

### <a name="remarks"></a>Notes

Une opération de bits peut uniquement servir à manipuler des bits dans les types de données `char` et `int`, et leurs variantes, et non pas sur des types de données plus complexes **float**, **double**, **longdouble**, `void`, `bool` ou autres.

L’opérateur de bits **NOT** a la même table de vérité que l’opérateur **NOT** logique, mais il s’applique au type de données au niveau des bits individuels. Étant donné le bit *b*, ~ *b* a la valeur true si *b* a la valeur false, et false si *b* a la valeur true. L’opérateur logique **NOT**[operator!](#op_not) s’applique au niveau d’un élément et compte toutes les valeurs différentes de zéro comme **true** : le résultat est un valarray de valeurs booléennes. L’opérateur de bits **NOToperator~**, en revanche, peut fournir un valarray de valeurs autres que 0 et 1, selon le résultat de l’opération de bits.

### <a name="example"></a>Exemple

```cpp
// valarray_op_bitnot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<unsigned short int> vaL1 ( 10 );
   valarray<unsigned short int> vaNOT1 ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL1 [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL1 [ i ] =  5*i;

   cout << "The initial valarray <unsigned short int> is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL1 [ i ] << " ";
   cout << ")." << endl;

   vaNOT1 = ~vaL1;
   cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT1 [ i ] << " ";
   cout << ")." << endl << endl;

   valarray<int> vaL2 ( 10 );
   valarray<int> vaNOT2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL2 [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL2 [ i ] =  -2 * i;

   cout << "The initial valarray <int> is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL2 [ i ] << " ";
   cout << ")." << endl;

   vaNOT2 = ~vaL2;
   cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT2 [ i ] << " ";
   cout << ")." << endl;

   // The negative numbers are represented using
   // the two's complement approach, so adding one
   // to the flipped bits returns the negative elements
   vaNOT2 = vaNOT2 + 1;
   cout << "The element-by-element result of "
        << "adding one\n is the negative of the "
        << "original elements the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT2 [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).
The element-by-element result of the bitwise NOT operator~ is the
 valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).

The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).
The element-by-element result of the bitwise NOT operator~ is the
 valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).
The element-by-element result of adding one
 is the negative of the original elements the
 valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).
*\
```

## <a name="resize"></a>  valarray::resize

Modifie le nombre d'éléments dans un valarray et lui affecte un nombre spécifié.

```cpp
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,
    const Type val);
```

### <a name="parameters"></a>Paramètres

`_Newsize` Le nombre d’éléments dans le valarray redimensionné.

`val` La valeur à attribuer aux éléments du valarray redimensionné.

### <a name="remarks"></a>Notes

La première fonction membre initialise les éléments avec leur constructeur par défaut.

Tous les pointeurs ou références aux éléments dans la séquence contrôlée sont invalidés.

### <a name="example"></a>Exemple

L'exemple suivant illustre l'utilisation de la fonction membre valarray::resize.

```cpp
// valarray_resize.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, sizeNew;

    valarray<int> va1(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;

    cout << "The valarray contains ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray is: "
         << size1  << "." <<endl << endl;

    va1.resize(15, 10);

    cout << "The valarray contains ( ";
        for (i = 0; i < 15; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;
    sizeNew = va1.size();
    cout << "The number of elements in the resized valarray is: "
         << sizeNew  << "." <<endl << endl;
}
```

```Output
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray is: 10.

The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).
The number of elements in the resized valarray is: 15.
```

## <a name="shift"></a>  valarray::shift

Décale tous les éléments dans un valarray d’un nombre spécifié d’emplacements.

```cpp
valarray<Type> shift(int count) const;
```

### <a name="parameters"></a>Paramètres

`count` Le nombre de décimales que les éléments doivent être décalés vers l’avant.

### <a name="return-value"></a>Valeur de retour

Un nouveau valarray dans lequel tous les éléments ont été déplacés de `count` emplacements vers l’avant du valarray, vers la gauche par rapport à leurs positions dans le valarray d’opérandes.

### <a name="remarks"></a>Notes

Une valeur positive de `count` décale les éléments vers la gauche de `count` emplacements, en complétant avec des zéros.

Une valeur négative de `count` décale les éléments vers la droite de `count` emplacements, en complétant avec des zéros.

### <a name="example"></a>Exemple

```cpp
// valarray_shift.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va1 ( 10 ), va2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va1 [ i ] =  i;
   for ( i = 0 ; i < 10 ; i += 1 )
      va2 [ i ] = 10 -  i;

   cout << "The operand valarray va1(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   // A positive parameter shifts elements left
   va1 = va1.shift ( 4 );
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   cout << "The operand valarray va2(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;

   // A negative parameter shifts elements right
   va2 = va2.shift ( - 4 );
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).
*\
```

## <a name="size"></a>  valarray::size

Recherche le nombre d'éléments dans un valarray.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Valeur de retour

Nombre d’éléments dans le valarray d’opérandes.

### <a name="example"></a>Exemple

L'exemple suivant illustre l'utilisation de la fonction membre valarray::size.

```cpp
// valarray_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, size2;

    valarray<int> va1(10), va2(12);
    for (i = 0; i < 10; i += 1)
        va1[i] =  i;
    for (i = 0; i < 10; i += 1)
        va2[i] =  i;

    cout << "The operand valarray va1(10) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray va1 is: va1.size = "
         << size1  << "." <<endl << endl;

    cout << "The operand valarray va2(12) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;

    size2 = va2.size();
    cout << "The number of elements in the valarray va2 is: va2.size = "
         << size2  << "." << endl << endl;

    // Initializing two more elements to va2
    va2[10] = 10;
    va2[11] = 11;
    cout << "After initializing two more elements,\n "
         << "the operand valarray va2(12) is now: ( ";
        for (i = 0; i < 12; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;
    cout << "The number of elements in the valarray va2 is still: "
         << size2  << "." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va1 is: va1.size = 10.

The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va2 is: va2.size = 12.

After initializing two more elements,
 the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).
The number of elements in the valarray va2 is still: 12.
```

## <a name="sum"></a>  valarray::sum

Détermine la somme de tous les éléments d’un valarray d’une longueur différente de zéro.

```cpp
Type sum() const;
```

### <a name="return-value"></a>Valeur de retour

La somme des éléments du valarray d’opérandes.

### <a name="remarks"></a>Notes

Si la longueur est supérieure à 1, la fonction membre ajoute les valeurs à la somme en appliquant `operator+=` entre les paires d’éléments de classe **Type**, opérateur qui, par conséquent, doit être fourni pour les éléments de type **Type**.

### <a name="example"></a>Exemple

```cpp
// valarray_sum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   int sumva = 0;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va (10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sumva = va.sum ( );
   cout << "The sum of elements in the valarray is: "
        << sumva  << "." <<endl;
}
\* Output:
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The sum of elements in the valarray is: 45.
*\
```

## <a name="swap"></a>  valarray::swap

Échange les éléments de deux `valarray`.

```cpp
void swap(valarray& right);
```

### <a name="parameters"></a>Paramètres

|Paramètre|Description|
|---------------|-----------------|
|`right`|`valarray` qui fournit les éléments à échanger.|

### <a name="remarks"></a>Notes

La fonction membre échange les séquences contrôlées entre `*this` et `right`. Elle le fait en temps constant, ne lève aucune exception et n'invalide aucune référence, pointeur ou itérateur qui désigne des éléments dans les deux séquences contrôlées.

## <a name="valarray"></a>  valarray::valarray

Construit un valarray de taille spécifique ou avec des éléments d’une valeur spécifique, ou comme copie d’un autre valarray ou comme sous-ensemble d’un autre valarray.

```cpp
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,
    size_t Count);

valarray(
    const Type* Ptr,
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```

### <a name="parameters"></a>Paramètres

`Count` Le nombre d’éléments dans le valarray.

`Val` La valeur à utiliser pour l’initialisation des éléments dans le valarray.

`Ptr` Pointeur vers les valeurs à utiliser pour initialiser les éléments dans le valarray.

`Right` Un valarray existant pour initialiser le nouveau valarray.

`SliceArray` Un slice_array dont les valeurs élément doivent être utilisées dans l’initialisation des éléments du valarray en cours de construction.

`GsliceArray` Un gslice_array dont les valeurs élément doivent être utilisées dans l’initialisation des éléments du valarray en cours de construction.

`MaskArray` Un mask_array dont les valeurs élément doivent être utilisées dans l’initialisation des éléments du valarray en cours de construction.

`IndArray` Un indirect_array dont les valeurs élément doivent être utilisées dans l’initialisation des éléments du valarray en cours de construction.

`IList` Initializer_list qui contient les éléments à copier.

### <a name="remarks"></a>Notes

Le premier constructeur (par défaut) initialise l’objet à un tableau vide. Les trois constructeurs suivants initialisent l’objet à un tableau de `Count` éléments comme suit :

- Pour le `valarray(size_t Count)` explicite, chaque élément est initialisé avec le constructeur par défaut.

- Pour `valarray(const Type& Val, Count)`, chaque élément est initialisé avec `Val`.

- Pour `valarray(const Type* Ptr, Count)`, l’élément à la position `I` est initialisé avec `Ptr`[ `I`].

Chaque constructeur restant initialise l’objet à un objet valarray\<Type> déterminé par le sous-ensemble spécifié dans l’argument.

Le dernier constructeur est le même que l’avant-dernier, mais avec un [déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Exemple

```cpp
// valarray_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    // The second member function
    valarray<int> va(10);
    for (auto i : va){
        va[i] = 2 * (i + 1);
    }

    cout << "The operand valarray va is:\n(";
    for (auto i : va) {
        cout << " " << va[i];
    }
    cout << " )" << endl;

    slice Slice(2, 4, 3);

    // The fifth member function
    valarray<int> vaSlice = va[Slice];

    cout << "The new valarray initialized from the slice is vaSlice ="
        << "\nva[slice( 2, 4, 3)] = (";
    for (int i = 0; i < 3; i++) {
        cout << " " << vaSlice[i];
    }
    cout << " )" << endl;

    valarray<int> va2{{ 1, 2, 3, 4 }};
    for (auto& v : va2){
        cout << v << " ";
    }
    cout << endl;
}

```

```Output
The operand valarray va is:( 0 2 2 2 2 2 2 2 2 2 )The new valarray initialized from the slice is vaSlice =va[slice( 2, 4, 3)] = ( 0 0 0 )1 2 3 4
```

## <a name="value_type"></a>  valarray::value_type

Type qui représente le type des éléments stockés dans un valarray.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Notes

Le type est un synonyme du paramètre de modèle **Type**.

### <a name="example"></a>Exemple

```cpp
// valarray_value_type.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // value_type declaration and initialization:
   valarray<int>::value_type Right = 10;

   cout << "The decalared value_type Right is: "
           << Right << endl;
   va *= Right;
   cout << "The resulting valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).
The decalared value_type Right is: 10
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).
*\
```

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
