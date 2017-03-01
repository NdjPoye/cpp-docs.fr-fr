---
title: poisson_distribution, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- poisson_distribution
- std::poisson_distribution
- random/std::poisson_distribution
- std::poisson_distribution::reset
- random/std::poisson_distribution::reset
- std::poisson_distribution::mean
- random/std::poisson_distribution::mean
- std::poisson_distribution::param
- random/std::poisson_distribution::param
- std::poisson_distribution::min
- random/std::poisson_distribution::min
- std::poisson_distribution::max
- random/std::poisson_distribution::max
- std::poisson_distribution::operator()
- random/std::poisson_distribution::operator()
- std::poisson_distribution::param_type
- random/std::poisson_distribution::param_type
- std::poisson_distribution::param_type::mean
- random/std::poisson_distribution::param_type::mean
- std::poisson_distribution::param_type::operator==
- random/std::poisson_distribution::param_type::operator==
- std::poisson_distribution::param_type::operator!=
- random/std::poisson_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- poisson_distribution class
ms.assetid: 09614281-349a-45f7-8e95-c0196be0a937
caps.latest.revision: 19
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
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 021eaec1ec55add912234f78bac0b9762b4a3444
ms.lasthandoff: 02/24/2017

---
# <a name="poissondistribution-class"></a>poisson_distribution, classe
Génère une probabilité d'une variable aléatoire suivant une loi de Poisson.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class IntType = int>
class poisson_distribution  
   {  
public:  
   // types  
   typedef IntType result_type;  
   struct param_type;  
   
   // constructors and reset functions  
   explicit poisson_distribution(double mean = 1.0);
   explicit poisson_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   double mean() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
``` 
  
#### <a name="parameters"></a>Paramètres  
*IntType*  
Le type des résultats entiers est `int` par défaut. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
La classe de modèle décrit une distribution qui produit des valeurs d'un type intégral spécifié par l'utilisateur avec une probabilité d'une variable aléatoire suivant une loi de Poisson. Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[poisson_distribution::poisson_distribution](#poisson_distribution__poisson_distribution)|`poisson_distribution::mean`|`poisson_distribution::param`|  
|`poisson_distribution::operator()`||[poisson_distribution::param_type](#poisson_distribution__param_type)|  
  
La fonction de propriété `mean()` retourne la valeur du paramètre de distribution stocké *mean*.  
  
Le membre de propriété `param()` définit ou retourne le package de paramètres de distribution stockés `param_type`.  

Les fonctions membres `min()` et `max()` retournent respectivement le plus petit et le plus grand résultat possible.  
  
La fonction membre `reset()` ignore toutes les valeurs mises en cache. Ainsi, le résultat de l’appel suivant à `operator()` ne dépend d’aucune valeur obtenue à partir du moteur avant l’appel.  
  
Les fonctions membres `operator()` retournent la valeur générée suivante d’après le moteur URNG, à partir du package de paramètres actuel ou spécifié.
  
Pour plus d’informations sur les classes de distribution et leurs membres, consultez [\<random>](../standard-library/random.md).  
  
Pour plus d’informations sur la distribution de Poisson, consultez l’article de Wolfram MathWorld [Poisson Distribution](http://go.microsoft.com/fwlink/LinkId=401112).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::poisson_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.mean() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double p_dist = 1.0;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
Premier test :  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 1.0000000000
Distribution for 100 samples:
    0 ::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::::::::::::::
    2 :::::::::::::::::::::::
    3 ::::::::
    5 :  
```  
  
Second test :  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 10
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 10.0000000000
Distribution for 100 samples:
    3 :
    4 ::
    5 ::
    6 ::::::::
    7 ::::
    8 ::::::::
    9 ::::::::::::::
   10 ::::::::::::
   11 ::::::::::::::::
   12 :::::::::::::::
   13 ::::::::
   14 ::::::
   15 :
   16 ::
   17 :  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
##  <a name="a-namepoissondistributionpoissondistributiona--poissondistributionpoissondistribution"></a><a name="poisson_distribution__poisson_distribution"></a>  poisson_distribution::poisson_distribution  
Construit la distribution.  
  
```  
explicit poisson_distribution(RealType mean = 1.0);
explicit binomial_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Paramètres  
*mean*  
Paramètre de distribution `mean`.  
  
*parm*  
Structure de paramètre utilisée pour construire la distribution.  
  
### <a name="remarks"></a>Notes  
 **Condition préalable :** `0.0 < mean`  
  
Le premier constructeur construit un objet dont la valeur `mean` stockée contient la valeur *mean*.  
  
Le deuxième constructeur construit un objet dont les paramètres stockés sont initialisés à partir de *parm*. Vous pouvez obtenir et définir les paramètres actuels d'une distribution existante en appelant la fonction membre `param()`.  
  
##  <a name="a-namepoissondistributionparamtypea--poissondistributionparamtype"></a><a name="poisson_distribution__param_type"></a>  poisson_distribution::param_type  
Stocke les paramètres de la distribution.  
  
```    
struct param_type {  
   typedef poisson_distribution<IntType> distribution_type;  
   param_type(double mean = 1.0);
   double mean() const;
     
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Paramètres  
Consultez les paramètres de constructeur pour [poisson_distribution](#poisson_distribution__poisson_distribution).  
  
### <a name="remarks"></a>Notes  
 **Condition préalable :** `0.0 < mean`  
  
Cette structure peut être passée au constructeur de classe de la distribution au moment de l'instanciation, à la fonction membre `param()` pour définir les paramètres stockés d'une distribution existante et à `operator()` pour une utilisation à la place des paramètres stockés.  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)


