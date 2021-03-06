---
title: gslice, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::gslice
- valarray/std::gslice::size
- valarray/std::gslice::start
- valarray/std::gslice::stride
dev_langs:
- C++
helpviewer_keywords:
- std::gslice [C++]
- std::gslice [C++], size
- std::gslice [C++], start
- std::gslice [C++], stride
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 127e1d4d39a79350dc050e1b9fb7636bce63c156
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="gslice-class"></a>gslice, classe

Classe utilitaire de valarray qui sert à définir des sous-ensembles multidimensionnels d'un valarray. Si un valarray est considéré comme une matrice multidimensionnelle avec tous les éléments dans un tableau, le secteur extrait un vecteur du tableau multidimensionnel.

## <a name="remarks"></a>Notes

La classe stocke les paramètres qui caractérisent un objet de type [gslice_array](../standard-library/gslice-array-class.md). Le sous-ensemble d’un valarray est construit indirectement quand un objet de classe gslice apparaît comme argument pour un objet de classe [valarray](../standard-library/valarray-class.md#op_at)**\<Type>**. Les valeurs stockées qui spécifient le sous-ensemble sélectionné à partir du valarray parent sont les suivantes :

- un index de départ ;

- Un vecteur de longueur de classe **valarray<size_t>**.

- Un vecteur stride de classe **valarray<size_t>**.

Les deux vecteurs doivent avoir la même longueur.

Si l'ensemble défini par un gslice est le sous-ensemble d'un valarray constant, le gslice est un nouveau valarray. Si l'ensemble défini par un gslice est le sous-ensemble d'un valarray non constant, le gslice a une sémantique de référence par rapport au valarray d'origine. Le mécanisme d'évaluation pour les valarrays non constants permet de gagner du temps et de la mémoire.

Les opérations sur les valarrays sont garanties uniquement si les sous-ensembles source et de destination définis par les gslices sont distincts et que tous les index sont valides.

### <a name="constructors"></a>Constructeurs

|Constructeur|Description|
|-|-|
|[gslice](#gslice)|Définit un sous-ensemble d'un `valarray` composé de plusieurs sections du `valarray` qui commencent toutes à un élément spécifié.|

### <a name="member-functions"></a>Fonctions membres

|Fonction membre|Description|
|-|-|
|[size](#size)|Recherche les valeurs de tableau spécifiant le nombre d'éléments dans un secteur général d'un `valarray`.|
|[start](#start)|Recherche l'index de départ d'un secteur général d'un `valarray`.|
|[stride](#stride)|Recherche la distance entre des éléments dans un secteur général d'un `valarray`.|

## <a name="requirements"></a>Spécifications

**En-tête :** \<valarray>

**Espace de noms :** std

## <a name="gslice"></a>  gslice::gslice

Classe utilitaire de valarray qui sert à définir des secteurs multidimensionnels d'un valarray.

```cpp
gslice();

gslice(
    size_t _StartIndex,
    const valarray<size_t>& _LenArray,
    const valarray<size_t>& _IncArray);
```

### <a name="parameters"></a>Paramètres

`_StartIndex` Index du premier élément dans le sous-ensemble valarray.

`_LenArray` Un tableau en spécifiant le nombre d’éléments dans chaque secteur.

`_IncArray` Un tableau en spécifiant la largeur de numérisation dans chaque secteur.

### <a name="return-value"></a>Valeur de retour

Le constructeur par défaut stocke zéro pour l’index de départ et les vecteurs de longueur nulle pour les vecteurs de longueur et stride. Le deuxième constructeur stocke `_StartIndex` pour l’index de départ, `_LenArray` pour le tableau de longueur et `_IncArray` pour le tableau stride.

### <a name="remarks"></a>Notes

**gslice** définit un sous-ensemble d’un valarray qui se compose de plusieurs sections du valarray, chacune commençant au même élément spécifié. La possibilité d’utiliser des tableaux pour définir plusieurs sections est la seule différence entre `gslice` et [slice::slice](../standard-library/slice-class.md#slice). La première section a un premier élément avec un index `_StartIndex`, un nombre d’éléments spécifié par le premier élément de `_LenArray` et un stride donné par le premier élément de `_IncArray`. L’ensemble de sections orthogonales suivant a ses premiers éléments donnés par la première section. Le deuxième élément de `_LenArray` spécifie le nombre d’éléments. Le stride est fourni par le deuxième élément de `_IncArray`. Une troisième dimension de sections prend les éléments du tableau à deux dimensions comme éléments de départ et procède de la même façon

### <a name="example"></a>Exemple

```cpp
// gslice_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:" << endl << "(";
   for ( i = 0 ; i < 20 ; i++ )
      cout << " " << va [ i ];
   cout << " )" << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];

   cout << "The valarray for vaGSlice is vaResult:" << endl
        << "va[vaGSlice] = (";

   for ( i = 0 ; i < 8 ; i++ )
      cout << " " << vaResult [ i ];
   cout << ")" << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 )
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19)
```

## <a name="size"></a>  gslice::size

Recherche les valeurs de tableau spécifiant le nombre d’éléments dans une section générale d’un valarray.

```cpp
valarray<size_t> size() const;
```

### <a name="return-value"></a>Valeur de retour

Valarray spécifiant le nombre d’éléments dans chaque section d’une section générale d’un valarray.

### <a name="remarks"></a>Notes

La fonction membre retourne les longueurs de sections stockées.

### <a name="example"></a>Exemple

```cpp
// gslice_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t sizeVA;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sizeVA = va.size ( );
   cout << "The size of the valarray is: "
        << sizeVA << "." << endl << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> sizeGS = vaGSlice.size ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The size of vaResult is:"
        << "\n vaGSlice.size ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << sizeGS[ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va is:
 ( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The size of the valarray is: 20.

The valarray for vaGSlice is vaResult:
 va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The size of vaResult is:
 vaGSlice.size ( ) = ( 4 4 ).
```

## <a name="start"></a>  gslice::start

Recherche l’index de départ d’une section générale d’un valarray.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Valeur de retour

Index de départ d’une section générale d’un valarray.

### <a name="example"></a>Exemple

```cpp
// gslice_start.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   size_t vaGSstart = vaGSlice.start ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The index of the first element of vaResult is: "
        << vaGSstart << "." << endl;
}
```

```Output
The operand valarray va is:
 ( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
 va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The index of the first element of vaResult is: 0.
```

## <a name="stride"></a>  gslice::stride

Recherche la distance entre des éléments dans une section générale d’un valarray.

```cpp
valarray<size_t> stride() const;
```

### <a name="return-value"></a>Valeur de retour

Valarray spécifiant la distance entre les éléments dans chaque section d’une section générale d’un valarray.

### <a name="example"></a>Exemple

```cpp
// gslice_stride.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for (i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> strideGS = vaGSlice.stride ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The strides of vaResult are:"
        << "\n vaGSlice.stride ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << strideGS[ i ] << " ";
   cout << ")." << endl;

}
```

```Output
The operand valarray va is:
 ( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
 va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The strides of vaResult are:
 vaGSlice.stride ( ) = ( 7 4 ).
```

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
