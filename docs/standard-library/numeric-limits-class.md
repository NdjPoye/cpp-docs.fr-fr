---
title: numeric_limits, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::numeric_limits
- std.numeric_limits
- numeric_limits
- limits/std::numeric_limits
dev_langs:
- C++
helpviewer_keywords:
- numeric_limits class
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
caps.latest.revision: 26
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4c58b23be2c5aae5969471370e52af1c5416d32e
ms.lasthandoff: 02/24/2017

---
# <a name="numericlimits-class"></a>numeric_limits, classe
La classe de modèle décrit les propriétés arithmétiques des types numériques intégrés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type>  
class numeric_limits  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Type`  
 Type de données fondamental des éléments dont les propriétés sont testées, interrogées ou définies.  
  
## <a name="remarks"></a>Notes  
 L'en-tête définit des spécialisations explicites pour les types `wchar_t`, `bool`, `char`, `signed char`, `unsigned char`, `short`, `unsigned short`, `int`, `unsigned int`, `long`, `unsigned long`, `float`, `double`, `long double`**,** `long long`, `unsigned long long`, `char16_t`et `char32_t`. Pour ces spécialisations explicites, le membre [numeric_limits::is_specialized](#numeric_limits__is_specialized) est `true`, et tous les membres concernés ont des valeurs significatives. Le programme peut fournir des spécialisations explicites supplémentaires. La plupart des fonctions membres de la classe décrivent ou testent les implémentations possibles de `float`.  
  
 Pour une spécialisation arbitraire, aucun membre n'a de valeur significative. Un objet membre qui n'a pas de valeur significative stocke zéro (ou `false`), tandis qu'une fonction membre qui ne retourne pas de valeur significative retourne `Type(0)`.  
  
### <a name="static-functions-and-constants"></a>Fonctions statiques et constantes  
  
|||  
|-|-|  
|[denorm_min](#numeric_limits__denorm_min)|Retourne la plus petite valeur dénormalisée différente de zéro.|  
|[digits](#numeric_limits__digits)|Retourne le nombre de chiffres de base que le type peut représenter sans perte de précision.|  
|[digits10](#numeric_limits__digits10)|Retourne le nombre de chiffres décimaux que le type peut représenter sans perte de précision.|  
|[epsilon](#numeric_limits__epsilon)|Retourne la différence entre 1 et la plus petite valeur supérieure à 1 que le type de données peut représenter.|  
|[has_denorm](#numeric_limits__has_denorm)|Teste si un type autorise les valeurs dénormalisées.|  
|[has_denorm_loss](#numeric_limits__has_denorm_loss)|Teste si une perte de précision est détectée comme une perte de dénormalisation et non pas comme un résultat inexact.|  
|[has_infinity](#numeric_limits__has_infinity)|Teste si un type a une représentation pour l'infini positif.|  
|[has_quiet_NaN](#numeric_limits__has_quiet_nan)|Teste si un type a une représentation pour un NaN (n'est pas un nombre) silencieux, qui ne fait pas de signalement.|  
|[has_signaling_NaN](#numeric_limits__has_signaling_nan)|Teste si un type a une représentation pour signaler un NaN (n'est pas un nombre).|  
|[infinity](#numeric_limits__infinity)|Représentation de l'infini positif pour un type, si elle est disponible.|  
|[is_bounded](#numeric_limits__is_bounded)|Teste si l'ensemble des valeurs qu'un type peut représenter est fini.|  
|[is_exact](#numeric_limits__is_exact)|Teste si les calculs effectués sur un type ne comportent pas d'erreurs d'arrondi.|  
|[is_iec559](#numeric_limits__is_iec559)|Teste si un type est conforme aux normes IEC 559.|  
|[is_integer](#numeric_limits__is_integer)|Teste si un type a une représentation des entiers.|  
|[is_modulo](#numeric_limits__is_modulo)|Teste si un type a une représentation du modulo.|  
|[is_signed](#numeric_limits__is_signed)|Teste si un type a une représentation signée.|  
|[is_specialized](#numeric_limits__is_specialized)|Teste si un type a une spécialisation explicite définie dans la classe de modèle `numeric_limits`.|  
|[lowest](#numeric_limits__lowest)|Retourne la plus grande valeur finie négative.|  
|[max](#numeric_limits__max)|Retourne la valeur finie maximale pour un type.|  
|[max_digits10](#numeric_limits__max_digits10)|Retourne le nombre de chiffres décimaux requis pour garantir que deux valeurs distinctes du type ont des représentations décimales distinctes.|  
|[max_exponent](#numeric_limits__max_exponent)|Retourne l'exposant entier positif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand un nombre exprimé dans une base de base (radix) est élevé à cette puissance.|  
|[max_exponent10](#numeric_limits__max_exponent10)|Retourne l'exposant entier positif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand une base&10; est élevée à cette puissance.|  
|[min](#numeric_limits__min)|Retourne la valeur normalisée minimale pour un type.|  
|[min_exponent](#numeric_limits__min_exponent)|Retourne l'exposant entier négatif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand un nombre exprimé dans une base de base (radix) est élevé à cette puissance.|  
|[min_exponent10](#numeric_limits__min_exponent10)|Retourne l'exposant entier négatif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand une base&10; est élevée à cette puissance.|  
|[quiet_NaN](#numeric_limits__quiet_nan)|Retourne la représentation d'un NaN (n'est pas un nombre) silencieux pour le type.|  
|[radix](#numeric_limits__radix)|Retourne la base entière, appelée base (radix), utilisée pour la représentation d'un type.|  
|[round_error](#numeric_limits__round_error)|Retourne l'erreur d'arrondi maximale pour le type.|  
|[round_style](#numeric_limits__round_style)|Retourne une valeur qui décrit les différentes méthodes qu'une implémentation peut choisir pour arrondir une valeur à virgule flottante en valeur entière.|  
|[signaling_NaN](#numeric_limits__signaling_nan)|Retourne la représentation d'un NaN (n'est pas un nombre) avec signalement pour le type.|  
|[tinyness_before](#numeric_limits__tinyness_before)|Teste si un type peut déterminer qu'une valeur est trop petite pour être représentée sous la forme d'une valeur normalisée avant d'être arrondie.|  
|[traps](#numeric_limits__traps)|Teste si les interceptions qui signalent des exceptions arithmétiques sont implémentées pour un type.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<limits>  
  
 **Espace de noms :** std  
  
##  <a name="a-namenumericlimitsdenormmina--numericlimitsdenormmin"></a><a name="numeric_limits__denorm_min"></a>  numeric_limits::denorm_min  
 Retourne la plus petite valeur dénormalisée différente de zéro.  
  
```  
static Type denorm_min() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Plus petite valeur dénormalisée différente de zéro.  
  
### <a name="remarks"></a>Notes  
 `long double` est similaire à **double** pour le compilateur C++.  
  
 La fonction retourne la valeur minimale pour le type, qui correspond à [min](#numeric_limits__min) si [has_denorm](#numeric_limits__has_denorm) n’est pas égal à **denorm_present**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_denorm_min.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The smallest nonzero denormalized value\n for float "  
        << "objects is: " << numeric_limits<float>::denorm_min( )   
        << endl;  
   cout << "The smallest nonzero denormalized value\n for double "  
        << "objects is: " << numeric_limits<double>::denorm_min( )   
        << endl;  
   cout << "The smallest nonzero denormalized value\n for long double "  
        << "objects is: " << numeric_limits<long double>::denorm_min( )   
        << endl;  
  
   // A smaller value will round to zero  
   cout << numeric_limits<float>::denorm_min( )/2 <<endl;  
   cout << numeric_limits<double>::denorm_min( )/2 <<endl;  
   cout << numeric_limits<long double>::denorm_min( )/2 <<endl;  
}  
```  
  
```Output  
The smallest nonzero denormalized value  
 for float objects is: 1.4013e-045  
The smallest nonzero denormalized value  
 for double objects is: 4.94066e-324  
The smallest nonzero denormalized value  
 for long double objects is: 4.94066e-324  
0  
0  
0  
```  
  
##  <a name="a-namenumericlimitsdigitsa--numericlimitsdigits"></a><a name="numeric_limits__digits"></a>  numeric_limits::digits  
 Retourne le nombre de chiffres de base que le type peut représenter sans perte de précision.  
  
```  
static const int digits = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de chiffres de base que le type peut représenter sans perte de précision.  
  
### <a name="remarks"></a>Notes  
 Le membre stocke le nombre de chiffres de base que le type peut représenter sans modification. Ce nombre est le nombre de bits autres qu’un bit de signe pour un type entier prédéfini ou le nombre de chiffres en mantisse pour un type à virgule flottante prédéfini.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_digits_min.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << numeric_limits<float>::digits <<endl;  
   cout << numeric_limits<double>::digits <<endl;  
   cout << numeric_limits<long double>::digits <<endl;  
   cout << numeric_limits<int>::digits <<endl;  
   cout << numeric_limits<__int64>::digits <<endl;  
}  
```  
  
```Output  
24  
53  
53  
31  
63  
```  
  
##  <a name="a-namenumericlimitsdigits10a--numericlimitsdigits10"></a><a name="numeric_limits__digits10"></a>  numeric_limits::digits10  
 Retourne le nombre de chiffres décimaux que le type peut représenter sans perte de précision.  
  
```  
static const int digits10 = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de chiffres décimaux que le type peut représenter sans perte de précision.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_digits10.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << numeric_limits<float>::digits10 <<endl;  
   cout << numeric_limits<double>::digits10 <<endl;  
   cout << numeric_limits<long double>::digits10 <<endl;  
   cout << numeric_limits<int>::digits10 <<endl;  
   cout << numeric_limits<__int64>::digits10 <<endl;  
   float f = (float)99999999;  
   cout.precision ( 10 );  
   cout << "The float is; " << f << endl;  
}  
```  
  
```Output  
6  
15  
15  
9  
18  
The float is; 100000000  
```  
  
##  <a name="a-namenumericlimitsepsilona--numericlimitsepsilon"></a><a name="numeric_limits__epsilon"></a>  numeric_limits::epsilon  
 La fonction retourne la différence entre 1 et la plus petite valeur supérieure à 1 qui peut être représentée pour le type de données.  
  
```  
static Type epsilon() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différence entre 1 et la plus petite valeur supérieure à 1 pouvant être représentée pour le type de données.  
  
### <a name="remarks"></a>Notes  
 La valeur est FLT_EPSILON pour le type **float**. `epsilon` pour un type est le plus petit nombre à virgule flottante positif *N* tel que *N* + `epsilon` + *N* peut être représenté.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_epsilon.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The difference between 1 and the smallest "  
        << "value greater than 1\n for float objects is: "   
        << numeric_limits<float>::epsilon( )   
        << endl;  
   cout << "The difference between 1 and the smallest "  
        << "value greater than 1\n for double objects is: "   
        << numeric_limits<double>::epsilon( )   
        << endl;  
   cout << "The difference between 1 and the smallest "  
        << "value greater than 1\n for long double objects is: "   
        << numeric_limits<long double>::epsilon( )   
        << endl;  
}  
```  
  
```Output  
The difference between 1 and the smallest value greater than 1  
 for float objects is: 1.19209e-007  
The difference between 1 and the smallest value greater than 1  
 for double objects is: 2.22045e-016  
The difference between 1 and the smallest value greater than 1  
 for long double objects is: 2.22045e-016  
```  
  
##  <a name="a-namenumericlimitshasdenorma--numericlimitshasdenorm"></a><a name="numeric_limits__has_denorm"></a>  numeric_limits::has_denorm  
 Teste si un type autorise les valeurs dénormalisées.  
  
```  
static const float_denorm_style has_denorm = denorm_absent;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur d’énumération de type **const**`float_denorm_style`, qui indique si le type accepte les valeurs dénormalisées.  
  
### <a name="remarks"></a>Notes  
 Le membre stocke **denorm_present** pour un type à virgule flottante qui a des valeurs dénormalisées, à savoir un nombre variable de bits d’exposant.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_has_denorm.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects allow denormalized values: "  
        << numeric_limits<float>::has_denorm   
        << endl;  
   cout << "Whether double objects allow denormalized values: "  
        << numeric_limits<double>::has_denorm   
        << endl;  
   cout << "Whether long int objects allow denormalized values: "   
        << numeric_limits<long int>::has_denorm   
        << endl;  
}  
```  
  
```Output  
Whether float objects allow denormalized values: 1  
Whether double objects allow denormalized values: 1  
Whether long int objects allow denormalized values: 0  
```  
  
##  <a name="a-namenumericlimitshasdenormlossa--numericlimitshasdenormloss"></a><a name="numeric_limits__has_denorm_loss"></a>  numeric_limits::has_denorm_loss  
 Teste si une perte de précision est détectée comme une perte de dénormalisation et non pas comme un résultat inexact.  
  
```  
static const bool has_denorm_loss = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si la perte de précision est détectée comme une perte de dénormalisation. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Le membre stocke la valeur true pour un type qui détermine si une valeur a perdu en précision parce qu’elle est fournie sous forme de résultat dénormalisé (trop petit pour être représenté en valeur normalisée) ou parce qu’elle est inexacte (différente d’un résultat qui n’est pas soumis aux limitations de la précision et d’une plage d’exposants), une option avec des représentations à virgule flottante IEC 559 pouvant affecter certains résultats.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_has_denorm_loss.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects can detect denormalized loss: "  
        << numeric_limits<float>::has_denorm_loss  
        << endl;  
   cout << "Whether double objects can detect denormalized loss: "  
        << numeric_limits<double>::has_denorm_loss  
        << endl;  
   cout << "Whether long int objects can detect denormalized loss: "   
        << numeric_limits<long int>::has_denorm_loss  
        << endl;  
}  
```  
  
```Output  
Whether float objects can detect denormalized loss: 1  
Whether double objects can detect denormalized loss: 1  
Whether long int objects can detect denormalized loss: 0  
```  
  
##  <a name="a-namenumericlimitshasinfinitya--numericlimitshasinfinity"></a><a name="numeric_limits__has_infinity"></a>  numeric_limits::has_infinity  
 Teste si un type a une représentation pour l'infini positif.  
  
```  
static const bool has_infinity = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a une représentation de l’infini positif. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Le membre retourne **true** si [is_iec559](#numeric_limits__is_iec559) est **true**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_has_infinity.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have infinity: "  
        << numeric_limits<float>::has_infinity  
        << endl;  
   cout << "Whether double objects have infinity: "  
        << numeric_limits<double>::has_infinity  
        << endl;  
   cout << "Whether long int objects have infinity: "   
        << numeric_limits<long int>::has_infinity  
        << endl;  
}  
```  
  
```Output  
Whether float objects have infinity: 1  
Whether double objects have infinity: 1  
Whether long int objects have infinity: 0  
```  
  
##  <a name="a-namenumericlimitshasquietnana--numericlimitshasquietnan"></a><a name="numeric_limits__has_quiet_nan"></a>  numeric_limits::has_quiet_NaN  
 Teste si un type a une représentation pour un NaN (n'est pas un nombre) silencieux, qui ne fait pas de signalement.  
  
```  
static const bool has_quiet_NaN = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le **type** a une représentation pour un NAN silencieux. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Un NAN silencieux représente une valeur qui n’est pas un nombre et qui ne signale pas sa présence dans une expression. La valeur de retour est **true** si [is_iec559](#numeric_limits__is_iec559) est true.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_has_quiet_nan.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have quiet_NaN: "  
        << numeric_limits<float>::has_quiet_NaN   
        << endl;  
   cout << "Whether double objects have quiet_NaN: "  
        << numeric_limits<double>::has_quiet_NaN   
        << endl;  
   cout << "Whether long int objects have quiet_NaN: "   
        << numeric_limits<long int>::has_quiet_NaN   
        << endl;  
}  
```  
  
```Output  
Whether float objects have quiet_NaN: 1  
Whether double objects have quiet_NaN: 1  
Whether long int objects have quiet_NaN: 0  
```  
  
##  <a name="a-namenumericlimitshassignalingnana--numericlimitshassignalingnan"></a><a name="numeric_limits__has_signaling_nan"></a>  numeric_limits::has_signaling_NaN  
 Teste si un type a une représentation pour signaler un NaN (n'est pas un nombre).  
  
```  
static const bool has_signaling_NaN = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a une représentation pour signaler un NaN. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Un NAN de signalisation représente une valeur qui n’est pas un nombre et qui signale sa présence dans une expression. La valeur de retour est **true** si [is_iec559](#numeric_limits__is_iec559) est true.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_has_signaling_nan.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have a signaling_NaN: "  
        << numeric_limits<float>::has_signaling_NaN   
        << endl;  
   cout << "Whether double objects have a signaling_NaN: "  
        << numeric_limits<double>::has_signaling_NaN   
        << endl;  
   cout << "Whether long int objects have a signaling_NaN: "   
        << numeric_limits<long int>::has_signaling_NaN   
        << endl;  
}  
```  
  
```Output  
Whether float objects have a signaling_NaN: 1  
Whether double objects have a signaling_NaN: 1  
Whether long int objects have a signaling_NaN: 0  
```  
  
##  <a name="a-namenumericlimitsinfinitya--numericlimitsinfinity"></a><a name="numeric_limits__infinity"></a>  numeric_limits::infinity  
 Représentation de l’infini positif pour un type, si elle est disponible.  
  
```  
static Type infinity() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Représentation de l’infini positif pour un type, si elle est disponible.  
  
### <a name="remarks"></a>Notes  
 La valeur de retour est significative uniquement si [has_infinity](#numeric_limits__has_infinity) est **true**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_infinity.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << numeric_limits<float>::has_infinity <<endl;  
   cout << numeric_limits<double>::has_infinity<<endl;  
   cout << numeric_limits<long double>::has_infinity <<endl;  
   cout << numeric_limits<int>::has_infinity <<endl;  
   cout << numeric_limits<__int64>::has_infinity <<endl;  
  
   cout << "The representation of infinity for type float is: "  
        << numeric_limits<float>::infinity( ) <<endl;  
   cout << "The representation of infinity for type double is: "  
        << numeric_limits<double>::infinity( ) <<endl;  
   cout << "The representation of infinity for type long double is: "  
        << numeric_limits<long double>::infinity( ) <<endl;  
}  
```  
  
```Output  
1  
1  
1  
0  
0  
The representation of infinity for type float is: 1.#INF  
The representation of infinity for type double is: 1.#INF  
The representation of infinity for type long double is: 1.#INF  
```  
  
##  <a name="a-namenumericlimitsisboundeda--numericlimitsisbounded"></a><a name="numeric_limits__is_bounded"></a>  numeric_limits::is_bounded  
 Teste si l'ensemble des valeurs qu'un type peut représenter est fini.  
  
```  
static const bool is_bounded = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a un ensemble délimité de valeurs pouvant être représentées. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Tous les types prédéfinis ont un ensemble délimité de valeurs pouvant être représentées et retournent **true**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_bounded.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have bounded set "  
        << "of representable values: "  
        << numeric_limits<float>::is_bounded  
        << endl;  
   cout << "Whether double objects have bounded set "  
        << "of representable values: "  
        << numeric_limits<double>::is_bounded  
        << endl;  
   cout << "Whether long int objects have bounded set "  
        << "of representable values: "  
        << numeric_limits<long int>::is_bounded  
        << endl;  
   cout << "Whether unsigned char objects have bounded set "  
        << "of representable values: "  
        << numeric_limits<unsigned char>::is_bounded  
        << endl;  
}  
```  
  
```Output  
Whether float objects have bounded set of representable values: 1  
Whether double objects have bounded set of representable values: 1  
Whether long int objects have bounded set of representable values: 1  
Whether unsigned char objects have bounded set of representable values: 1  
```  
  
##  <a name="a-namenumericlimitsisexacta--numericlimitsisexact"></a><a name="numeric_limits__is_exact"></a>  numeric_limits::is_exact  
 Teste si les calculs effectués sur un type ne comportent pas d'erreurs d'arrondi.  
  
```  
static const bool is_exact = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les calculs ne comportent pas d’erreurs d’arrondi. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Tous les types d’entiers prédéfinis ont des représentations exactes de leurs valeurs et retournent **false**. Une représentation rationnelle ou à virgule fixe est également considérée comme exacte, mais ce n’est pas le cas d’une représentation à virgule flottante.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_exact.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have calculations "  
        << "free of rounding errors: "  
        << numeric_limits<float>::is_exact  
        << endl;  
   cout << "Whether double objects have calculations "  
        << "free of rounding errors: "  
        << numeric_limits<double>::is_exact  
        << endl;  
   cout << "Whether long int objects have calculations "  
        << "free of rounding errors: "  
        << numeric_limits<long int>::is_exact  
        << endl;  
   cout << "Whether unsigned char objects have calculations "  
        << "free of rounding errors: "  
        << numeric_limits<unsigned char>::is_exact  
        << endl;  
}  
```  
  
```Output  
Whether float objects have calculations free of rounding errors: 0  
Whether double objects have calculations free of rounding errors: 0  
Whether long int objects have calculations free of rounding errors: 1  
Whether unsigned char objects have calculations free of rounding errors: 1  
```  
  
##  <a name="a-namenumericlimitsisiec559a--numericlimitsisiec559"></a><a name="numeric_limits__is_iec559"></a>  numeric_limits::is_iec559  
 Teste si un type est conforme aux normes IEC 559.  
  
```  
static const bool is_iec559 = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type est conforme à la norme IEC 559. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 La norme IEC 559 est une norme internationale pour représenter les valeurs à virgule flottante. Elle est également appelée IEEE 754 aux États-Unis.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_iec559.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects conform to iec559 standards: "  
        << numeric_limits<float>::is_iec559  
        << endl;  
   cout << "Whether double objects conform to iec559 standards: "  
        << numeric_limits<double>::is_iec559  
        << endl;  
   cout << "Whether int objects conform to iec559 standards: "  
        << numeric_limits<int>::is_iec559  
        << endl;  
   cout << "Whether unsigned char objects conform to iec559 standards: "  
        << numeric_limits<unsigned char>::is_iec559  
        << endl;  
}  
```  
  
```Output  
Whether float objects conform to iec559 standards: 1  
Whether double objects conform to iec559 standards: 1  
Whether int objects conform to iec559 standards: 0  
Whether unsigned char objects conform to iec559 standards: 0  
```  
  
##  <a name="a-namenumericlimitsisintegera--numericlimitsisinteger"></a><a name="numeric_limits__is_integer"></a>  numeric_limits::is_integer  
 Teste si un type a une représentation des entiers.  
  
```  
static const bool is_integer = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a une représentation des entiers. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Tous les types d’entiers prédéfinis ont une représentation des entiers.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_integer.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have an integral representation: "  
        << numeric_limits<float>::is_integer  
        << endl;  
   cout << "Whether double objects have an integral representation: "  
        << numeric_limits<double>::is_integer  
        << endl;  
   cout << "Whether int objects have an integral representation: "  
        << numeric_limits<int>::is_integer  
        << endl;  
   cout << "Whether unsigned char objects have an integral representation: "  
        << numeric_limits<unsigned char>::is_integer  
        << endl;  
}  
```  
  
```Output  
Whether float objects have an integral representation: 0  
Whether double objects have an integral representation: 0  
Whether int objects have an integral representation: 1  
Whether unsigned char objects have an integral representation: 1  
```  
  
##  <a name="a-namenumericlimitsismoduloa--numericlimitsismodulo"></a><a name="numeric_limits__is_modulo"></a>  numeric_limits::is_modulo  
 Teste si un **type** a une représentation du modulo.  
  
```  
static const bool is_modulo = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a une représentation du modulo. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Une représentation du modulo est une représentation où tous les résultats sont une réduction modulo d’une certaine valeur. Tous les types d’entiers non signés prédéfinis ont une représentation du modulo.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_modulo.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have a modulo representation: "  
        << numeric_limits<float>::is_modulo  
        << endl;  
   cout << "Whether double objects have a modulo representation: "  
        << numeric_limits<double>::is_modulo  
        << endl;  
   cout << "Whether signed char objects have a modulo representation: "  
        << numeric_limits<signed char>::is_modulo  
        << endl;  
   cout << "Whether unsigned char objects have a modulo representation: "  
        << numeric_limits<unsigned char>::is_modulo  
        << endl;  
}  
```  
  
```Output  
Whether float objects have a modulo representation: 0  
Whether double objects have a modulo representation: 0  
Whether signed char objects have a modulo representation: 1  
Whether unsigned char objects have a modulo representation: 1  
```  
  
##  <a name="a-namenumericlimitsissigneda--numericlimitsissigned"></a><a name="numeric_limits__is_signed"></a>  numeric_limits::is_signed  
 Teste si un type a une représentation signée.  
  
```  
static const bool is_signed = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a une représentation signée. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Le membre stocke la valeur true pour un type qui a une représentation signée, ce qui est le cas pour tous les types d’entiers signés et types à virgule flottante prédéfinis.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_signaled.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have a signed representation: "  
        << numeric_limits<float>::is_signed  
        << endl;  
   cout << "Whether double objects have a signed representation: "  
        << numeric_limits<double>::is_signed  
        << endl;  
   cout << "Whether signed char objects have a signed representation: "  
        << numeric_limits<signed char>::is_signed  
        << endl;  
   cout << "Whether unsigned char objects have a signed representation: "  
        << numeric_limits<unsigned char>::is_signed  
        << endl;  
}  
```  
  
```Output  
Whether float objects have a signed representation: 1  
Whether double objects have a signed representation: 1  
Whether signed char objects have a signed representation: 1  
Whether unsigned char objects have a signed representation: 0  
```  
  
##  <a name="a-namenumericlimitsisspecializeda--numericlimitsisspecialized"></a><a name="numeric_limits__is_specialized"></a>  numeric_limits::is_specialized  
 Teste si un type a une spécialisation explicite définie dans la classe de modèle `numeric_limits`.  
  
```  
static const bool is_specialized = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le type a une spécialisation explicite définie dans la classe de modèle. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Tous les types scalaires autres que les pointeurs ont une spécialisation explicite définie dans la classe de modèle `numeric_limits`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_is_specialized.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float objects have an explicit "  
        << "specialization in the class: "  
        << numeric_limits<float>::is_specialized  
        << endl;  
   cout << "Whether float* objects have an explicit "  
        << "specialization in the class: "  
        << numeric_limits<float*>::is_specialized  
        << endl;  
   cout << "Whether int objects have an explicit "  
        << "specialization in the class: "  
        << numeric_limits<int>::is_specialized  
        << endl;  
   cout << "Whether int* objects have an explicit "  
        << "specialization in the class: "  
        << numeric_limits<int*>::is_specialized  
        << endl;  
}  
```  
  
```Output  
Whether float objects have an explicit specialization in the class: 1  
Whether float* objects have an explicit specialization in the class: 0  
Whether int objects have an explicit specialization in the class: 1  
Whether int* objects have an explicit specialization in the class: 0  
```  
  
##  <a name="a-namenumericlimitslowesta--numericlimitslowest"></a><a name="numeric_limits__lowest"></a>  numeric_limits::lowest  
 Retourne la plus grande valeur finie négative.  
  
```  
static Type lowest() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la plus grande valeur finie négative.  
  
### <a name="remarks"></a>Notes  
 Retourne la plus grande valeur finie négative pour le type (en général, `min` `()` pour les types entiers et `-``max` `()` pour les types à virgule flottante). La valeur de retour est significative si `is_bounded` a pour valeur `true`.  
  
##  <a name="a-namenumericlimitsmaxa--numericlimitsmax"></a><a name="numeric_limits__max"></a>  numeric_limits::max  
 Retourne la valeur finie maximale pour un type.  
  
```  
static Type max() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur finie maximale pour un type.  
  
### <a name="remarks"></a>Notes  
 La valeur finie maximale est INT_MAX pour le type `int` et FLT_MAX pour le type **float**. La valeur de retour est significative si [is_bounded](#numeric_limits__is_bounded) est **true**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_max.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main() {  
   cout << "The maximum value for type float is:  "  
        << numeric_limits<float>::max( )  
        << endl;  
   cout << "The maximum value for type double is:  "  
        << numeric_limits<double>::max( )  
        << endl;  
   cout << "The maximum value for type int is:  "  
        << numeric_limits<int>::max( )  
        << endl;  
   cout << "The maximum value for type short int is:  "  
        << numeric_limits<short int>::max( )  
        << endl;  
}  
```  
  
##  <a name="a-namenumericlimitsmaxdigits10a--numericlimitsmaxdigits10"></a><a name="numeric_limits__max_digits10"></a>  numeric_limits::max_digits10  
 Retourne le nombre de chiffres décimaux nécessaires pour s'assurer que deux valeurs distinctes du type ont des représentations décimales distinctes.  
  
```  
static int max_digits10 = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de chiffres décimaux nécessaires pour s'assurer que deux valeurs distinctes du type ont des représentations décimales distinctes.  
  
### <a name="remarks"></a>Notes  
 Le membre stocke retourne le nombre de chiffres décimaux nécessaires pour s'assurer que deux valeurs distinctes du type ont des représentations décimales distinctes.  
  
##  <a name="a-namenumericlimitsmaxexponenta--numericlimitsmaxexponent"></a><a name="numeric_limits__max_exponent"></a>  numeric_limits::max_exponent  
 Retourne l'exposant entier positif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand un nombre exprimé dans une base de base (radix) est élevé à cette puissance.  
  
```  
static const int max_exponent = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Exposant de base entier maximal qui peut être représenté par le type.  
  
### <a name="remarks"></a>Notes  
 La valeur retournée par la fonction membre est significative uniquement pour les types à virgule flottante. `max_exponent` est la valeur FLT_MAX_EXP pour le type **float**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_max_exponent.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The maximum radix-based exponent for type float is:  "  
        << numeric_limits<float>::max_exponent  
        << endl;  
   cout << "The maximum radix-based exponent for type double is:  "  
        << numeric_limits<double>::max_exponent  
        << endl;  
   cout << "The maximum radix-based exponent for type long double is:  "  
        << numeric_limits<long double>::max_exponent  
        << endl;  
}  
```  
  
```Output  
The maximum radix-based exponent for type float is:  128  
The maximum radix-based exponent for type double is:  1024  
The maximum radix-based exponent for type long double is:  1024  
```  
  
##  <a name="a-namenumericlimitsmaxexponent10a--numericlimitsmaxexponent10"></a><a name="numeric_limits__max_exponent10"></a>  numeric_limits::max_exponent10  
 Retourne l'exposant entier positif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand une base&10; est élevée à cette puissance.  
  
```  
static const int max_exponent10 = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Exposant entier maximal de base 10 qui peut être représenté par le type.  
  
### <a name="remarks"></a>Notes  
 La valeur retournée par la fonction membre est significative uniquement pour les types à virgule flottante. `max_exponent` est la valeur FLT_MAX_10 pour le type **float**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_max_exponent10.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The maximum base 10 exponent for type float is:  "  
           << numeric_limits<float>::max_exponent10  
           << endl;  
   cout << "The maximum base 10 exponent for type double is:  "  
           << numeric_limits<double>::max_exponent10  
           << endl;  
   cout << "The maximum base 10 exponent for type long double is:  "  
           << numeric_limits<long double>::max_exponent10  
           << endl;  
}  
```  
  
```Output  
The maximum base 10 exponent for type float is:  38  
The maximum base 10 exponent for type double is:  308  
The maximum base 10 exponent for type long double is:  308  
```  
  
##  <a name="a-namenumericlimitsmina--numericlimitsmin"></a><a name="numeric_limits__min"></a>  numeric_limits::min  
 Retourne la valeur normalisée minimale pour un type.  
  
```  
static Type min() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur normalisée minimale pour le type.  
  
### <a name="remarks"></a>Notes  
 La valeur normalisée minimale est INT_MIN pour le type `int` et FLT_MIN pour le type `float`. La valeur de retour est significative si [is_bounded](#numeric_limits__is_bounded) est `true` ou si [is_signed](#numeric_limits__is_signed) est `false`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_min.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The minimum value for type float is:  "  
        << numeric_limits<float>::min( )  
        << endl;  
   cout << "The minimum value for type double is:  "  
        << numeric_limits<double>::min( )  
        << endl;  
   cout << "The minimum value for type int is:  "  
        << numeric_limits<int>::min( )  
        << endl;  
   cout << "The minimum value for type short int is:  "  
        << numeric_limits<short int>::min( )  
        << endl;  
}  
```  
  
```Output  
The minimum value for type float is:  1.17549e-038  
The minimum value for type double is:  2.22507e-308  
The minimum value for type int is:  -2147483648  
The minimum value for type short int is:  -32768  
```  
  
##  <a name="a-namenumericlimitsminexponenta--numericlimitsminexponent"></a><a name="numeric_limits__min_exponent"></a>  numeric_limits::min_exponent  
 Retourne l'exposant entier négatif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand un nombre exprimé dans une base de base (radix) est élevé à cette puissance.  
  
```  
static const int min_exponent = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Exposant de base entier minimal qui peut être représenté par le type.  
  
### <a name="remarks"></a>Notes  
 La fonction membre est significative uniquement pour les types à virgule flottante. `min_exponent` est la valeur FLT_MIN_EXP pour le type **float**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_min_exponent.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The minimum radix-based exponent for type float is:  "  
        << numeric_limits<float>::min_exponent  
        << endl;  
   cout << "The minimum radix-based exponent for type double is:  "  
        << numeric_limits<double>::min_exponent  
        << endl;  
   cout << "The minimum radix-based exponent for type long double is:  "  
         << numeric_limits<long double>::min_exponent  
        << endl;  
}  
```  
  
```Output  
The minimum radix-based exponent for type float is:  -125  
The minimum radix-based exponent for type double is:  -1021  
The minimum radix-based exponent for type long double is:  -1021  
```  
  
##  <a name="a-namenumericlimitsminexponent10a--numericlimitsminexponent10"></a><a name="numeric_limits__min_exponent10"></a>  numeric_limits::min_exponent10  
 Retourne l'exposant entier négatif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand une base&10; est élevée à cette puissance.  
  
```  
static const int min_exponent10 = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Exposant entier minimal de base 10 qui peut être représenté par le type.  
  
### <a name="remarks"></a>Notes  
 La fonction membre est significative uniquement pour les types à virgule flottante. `min_exponent10` est la valeur FLT_MIN_10_EXP pour le type **float**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_min_exponent10.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The minimum base 10 exponent for type float is:  "  
        << numeric_limits<float>::min_exponent10  
        << endl;  
   cout << "The minimum base 10 exponent for type double is:  "  
        << numeric_limits<double>::min_exponent10  
        << endl;  
   cout << "The minimum base 10 exponent for type long double is:  "  
        << numeric_limits<long double>::min_exponent10  
        << endl;  
}  
```  
  
```Output  
The minimum base 10 exponent for type float is:  -37  
The minimum base 10 exponent for type double is:  -307  
The minimum base 10 exponent for type long double is:  -307  
```  
  
##  <a name="a-namenumericlimitsquietnana--numericlimitsquietnan"></a><a name="numeric_limits__quiet_nan"></a>  numeric_limits::quiet_NaN  
 Retourne la représentation d'un NaN (n'est pas un nombre) silencieux pour le type.  
  
```  
static Type quiet_NaN() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Représentation d’un NaN silencieux pour le type.  
  
### <a name="remarks"></a>Notes  
 La valeur de retour est significative uniquement si [has_quiet_NaN](#numeric_limits__has_quiet_nan) est **true**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_quiet_nan.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The quiet NaN for type float is:  "  
        << numeric_limits<float>::quiet_NaN( )  
        << endl;  
   cout << "The quiet NaN for type int is:  "  
        << numeric_limits<int>::quiet_NaN( )  
        << endl;  
   cout << "The quiet NaN for type long double is:  "  
        << numeric_limits<long double>::quiet_NaN( )  
        << endl;  
}  
```  
  
```Output  
The quiet NaN for type float is:  1.#QNAN  
The quiet NaN for type int is:  0  
The quiet NaN for type long double is:  1.#QNAN  
```  
  
##  <a name="a-namenumericlimitsradixa--numericlimitsradix"></a><a name="numeric_limits__radix"></a>  numeric_limits::radix  
 Retourne la base entière, appelée base (radix), utilisée pour la représentation d'un type.  
  
```  
static const int radix = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Base entière utilisée pour la représentation du type.  
  
### <a name="remarks"></a>Notes  
 La base utilisée est la base 2 pour les types entiers prédéfinis, et la base à laquelle l’exposant est élevé, ou FLT_RADIX, pour les types à virgule flottante prédéfinis.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_radix.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The base for type float is:  "  
        << numeric_limits<float>::radix  
        << endl;  
   cout << "The base for type int is:  "  
        << numeric_limits<int>::radix  
        << endl;  
   cout << "The base for type long double is:  "  
        << numeric_limits<long double>::radix  
        << endl;  
}  
```  
  
```Output  
The base for type float is:  2  
The base for type int is:  2  
The base for type long double is:  2  
```  
  
##  <a name="a-namenumericlimitsrounderrora--numericlimitsrounderror"></a><a name="numeric_limits__round_error"></a>  numeric_limits::round_error  
 Retourne l'erreur d'arrondi maximale pour le type.  
  
```  
static Type round_error() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Erreur d’arrondi maximale pour le type.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_round_error.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The maximum rounding error for type float is:  "  
        << numeric_limits<float>::round_error( )  
        << endl;  
   cout << "The maximum rounding error for type int is:  "  
        << numeric_limits<int>::round_error( )  
        << endl;  
   cout << "The maximum rounding error for type long double is:  "  
        << numeric_limits<long double>::round_error( )  
        << endl;  
}  
```  
  
```Output  
The maximum rounding error for type float is:  0.5  
The maximum rounding error for type int is:  0  
The maximum rounding error for type long double is:  0.5  
```  
  
##  <a name="a-namenumericlimitsroundstylea--numericlimitsroundstyle"></a><a name="numeric_limits__round_style"></a>  numeric_limits::round_style  
 Retourne une valeur qui décrit les différentes méthodes qu'une implémentation peut choisir pour arrondir une valeur à virgule flottante en valeur entière.  
  
```  
static const float_round_style round_style = round_toward_zero;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur retournée par l’énumération `float_round_style` qui décrit le style d’arrondi.  
  
### <a name="remarks"></a>Notes  
 Le membre stocke une valeur qui décrit les différentes méthodes qu’une implémentation peut choisir pour arrondir une valeur à virgule flottante en valeur entière.  
  
 Le style d’arrondi est codé en dur dans cette implémentation. Même si le programme démarre avec un mode d’arrondi différent, cette valeur ne change donc pas.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_round_style.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <float.h>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The rounding style for a double type is: "   
        << numeric_limits<double>::round_style << endl;  
   _controlfp_s(NULL,_RC_DOWN,_MCW_RC );  
   cout << "The rounding style for a double type is now: "   
        << numeric_limits<double>::round_style << endl;  
   cout << "The rounding style for an int type is: "   
        << numeric_limits<int>::round_style << endl;  
}  
```  
  
```Output  
The rounding style for a double type is: 1  
The rounding style for a double type is now: 1  
The rounding style for an int type is: 0  
```  
  
##  <a name="a-namenumericlimitssignalingnana--numericlimitssignalingnan"></a><a name="numeric_limits__signaling_nan"></a>  numeric_limits::signaling_NaN  
 Retourne la représentation d'un NaN (n'est pas un nombre) avec signalement pour le type.  
  
```  
static Type signaling_NaN() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Représentation d’un NaN avec signalement pour le type.  
  
### <a name="remarks"></a>Notes  
 La valeur de retour est significative uniquement si [has_signaling_NaN](#numeric_limits__has_signaling_nan) est **true**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_signaling_nan.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "The signaling NaN for type float is:  "  
        << numeric_limits<float>::signaling_NaN( )  
        << endl;  
   cout << "The signaling NaN for type int is:  "  
        << numeric_limits<int>::signaling_NaN( )  
        << endl;  
   cout << "The signaling NaN for type long double is:  "  
        << numeric_limits<long double>::signaling_NaN( )  
        << endl;  
}  
```  
  
##  <a name="a-namenumericlimitstinynessbeforea--numericlimitstinynessbefore"></a><a name="numeric_limits__tinyness_before"></a>  numeric_limits::tinyness_before  
 Teste si un type peut déterminer qu'une valeur est trop petite pour être représentée sous la forme d'une valeur normalisée avant d'être arrondie.  
  
```  
static const bool tinyness_before = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si le type peut détecter les valeurs très petites avant d’être arrondies. `false` dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Les types qui peuvent détecter les valeurs très petites étaient inclus en option avec les représentations à virgule flottante IEC 559. Leur implémentation peut affecter certains résultats.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_tinyness_before.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float types can detect tinyness before rounding: "  
        << numeric_limits<float>::tinyness_before  
        << endl;  
   cout << "Whether double types can detect tinyness before rounding: "  
        << numeric_limits<double>::tinyness_before  
        << endl;  
   cout << "Whether long int types can detect tinyness before rounding: "  
        << numeric_limits<long int>::tinyness_before  
        << endl;  
   cout << "Whether unsigned char types can detect tinyness before rounding: "  
        << numeric_limits<unsigned char>::tinyness_before  
        << endl;  
}  
```  
  
```Output  
Whether float types can detect tinyness before rounding: 1  
Whether double types can detect tinyness before rounding: 1  
Whether long int types can detect tinyness before rounding: 0  
Whether unsigned char types can detect tinyness before rounding: 0  
```  
  
##  <a name="a-namenumericlimitstrapsa--numericlimitstraps"></a><a name="numeric_limits__traps"></a>  numeric_limits::traps  
 Teste si les interceptions qui signalent des exceptions arithmétiques sont implémentées pour un type.  
  
```  
static const bool traps = false;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les interceptions sont implémentées pour le type. **false** dans le cas contraire.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// numeric_limits_traps.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <limits>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Whether float types have implemented trapping: "  
        << numeric_limits<float>::traps  
        << endl;  
   cout << "Whether double types have implemented trapping: "  
        << numeric_limits<double>::traps  
        << endl;  
   cout << "Whether long int types have implemented trapping: "  
        << numeric_limits<long int>::traps  
        << endl;  
   cout << "Whether unsigned char types have implemented trapping: "  
        << numeric_limits<unsigned char>::traps  
        << endl;  
}  
```  
  
```Output  
Whether float types have implemented trapping: 1  
Whether double types have implemented trapping: 1  
Whether long int types have implemented trapping: 0  
Whether unsigned char types have implemented trapping: 0  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

