---
title: exponential_distribution, classe │ Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::exponential_distribution
- random/std::exponential_distribution::reset
- random/std::exponential_distribution::lambda
- random/std::exponential_distribution::param
- random/std::exponential_distribution::min
- random/std::exponential_distribution::max
- random/std::exponential_distribution::operator()
- random/std::exponential_distribution::param_type
- random/std::exponential_distribution::param_type::lambda
- random/std::exponential_distribution::param_type::operator==
- random/std::exponential_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::exponential_distribution [C++]
- std::exponential_distribution [C++], reset
- std::exponential_distribution [C++], lambda
- std::exponential_distribution [C++], param
- std::exponential_distribution [C++], min
- std::exponential_distribution [C++], max
- std::exponential_distribution [C++], param_type
- std::exponential_distribution [C++], param_type
ms.assetid: d54f3126-a09b-45f9-a30b-0d94d03bcdc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f324eaea0f84767d174bb109a8c1cfff7abfb50
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="exponentialdistribution-class"></a>exponential_distribution, classe

Génère une distribution exponentielle.

## <a name="syntax"></a>Syntaxe

```cpp
template<class RealType = double>
class exponential_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructors and reset functions
   explicit exponential_distribution(result_type lambda = 1.0);
   explicit exponential_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type lambda() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Paramètres

*RealType* par défaut est le type de résultat à virgule flottante, `double`. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).

*URNG* Le moteur de génération de nombres aléatoires. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Notes

La classe de modèle décrit une distribution qui produit des valeurs d'un type intégral spécifié par l'utilisateur, ou du type `double` si aucun n'est fourni, distribuées selon une loi exponentielle. Le tableau suivant contient des liens vers des articles sur différents membres.

||||
|-|-|-|
|[exponential_distribution](#exponential_distribution)|`exponential_distribution::lambda`|`exponential_distribution::param`|
|`exponential_distribution::operator()`||[param_type](#param_type)|

La fonction membre de propriété `lambda()` retourne la valeur du paramètre de distribution stocké `lambda`.

La fonction membre de propriété `param()` définit ou retourne le package de paramètres de distribution stockés `param_type`.

Pour plus d’informations sur les classes de distribution et leurs membres, consultez [\<random>](../standard-library/random.md).

Pour plus d’informations sur la distribution exponentielle, consultez l’article de Wolfram MathWorld [Exponential Distribution](http://go.microsoft.com/fwlink/p/?linkid=401098).

## <a name="example"></a>Exemple

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double l, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;
    std::mt19937 gen(1701);

    std::exponential_distribution<> distr(l);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "lambda() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.lambda() << std::endl;

    // generate the distribution as a histogram
    std::map<double, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    int counter = 0;
    for (const auto& elem : histogram) {
        std::cout << std::fixed << std::setw(11) << ++counter << ": "
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double l_dist = 0.5;
    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): ";
    std::cin >> l_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(l_dist, samples);
}

```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
lambda() == 1.0000000000
Distribution for 10 samples:
    1: 0.0936880533
    2: 0.1225944894
    3: 0.6443593183
    4: 0.6551171649
    5: 0.7313457551
    6: 0.7313557977
    7: 0.7590097389
    8: 1.4466885214
    9: 1.6434088411
    10: 2.1201210996
```

## <a name="requirements"></a>Spécifications

**En-tête :** \<random>

**Espace de noms :** std

## <a name="exponential_distribution"></a>  exponential_distribution::exponential_distribution

Construit la distribution.

```cpp
explicit exponential_distribution(result_type lambda = 1.0);
explicit exponential_distribution(const param_type& parm);
```

### <a name="parameters"></a>Paramètres

*lambda* le `lambda` paramètre de distribution.

*parm* package de paramètres utilisé pour construire la distribution.

### <a name="remarks"></a>Notes

**Condition préalable :** `0.0 < lambda`

Le premier constructeur construit un objet dont la valeur `lambda` stockée contient la valeur *lambda*.

Le deuxième constructeur construit un objet dont les paramètres stockés sont initialisés à partir de *parm*. Vous pouvez obtenir et définir les paramètres actuels d'une distribution existante en appelant la fonction membre `param()`.

## <a name="param_type"></a>  exponential_distribution::param_type

Stocke les paramètres de la distribution.

```cpp
struct param_type {
   typedef exponential_distribution<result_type> distribution_type;
   param_type(result_type lambda = 1.0);
   result_type lambda() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Paramètres

*lambda* le `lambda` paramètre de distribution.

*droit* le `param_type` à comparer à cet objet.

### <a name="remarks"></a>Notes

**Condition préalable :** `0.0 < lambda`

Cette structure peut être passée au constructeur de classe de la distribution au moment de l'instanciation, à la fonction membre `param()` pour définir les paramètres stockés d'une distribution existante et à `operator()` pour une utilisation à la place des paramètres stockés.

## <a name="see-also"></a>Voir aussi

[\<random>](../standard-library/random.md)<br/>
