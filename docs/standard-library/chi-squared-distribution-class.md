---
title: "chi_squared_distribution, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chi_squared_distribution
- std::chi_squared_distribution
- random/std::chi_squared_distribution
- std::chi_squared_distribution::reset
- random/std::chi_squared_distribution::reset
- std::chi_squared_distribution::n
- random/std::chi_squared_distribution::n
- std::chi_squared_distribution::param
- random/std::chi_squared_distribution::param
- std::chi_squared_distribution::min
- random/std::chi_squared_distribution::min
- std::chi_squared_distribution::max
- random/std::chi_squared_distribution::max
- std::chi_squared_distribution::operator()
- random/std::chi_squared_distribution::operator()
- std::chi_squared_distribution::param_type
- random/std::chi_squared_distribution::param_type
- std::chi_squared_distribution::param_type::n
- random/std::chi_squared_distribution::param_type::n
- std::chi_squared_distribution::param_type::operator==
- random/std::chi_squared_distribution::param_type::operator==
- std::chi_squared_distribution::param_type::operator!=
- random/std::chi_squared_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- chi_squared_distribution class
ms.assetid: 9b603fbe-cafd-4a92-b8c5-a434d60b8122
caps.latest.revision: 17
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
ms.sourcegitcommit: c7f3b346bc8abeab0c6bd913fc0b554bef4ed208
ms.openlocfilehash: 5e60b73c22a7704f63f70ae2e6498fc6e47dde1e
ms.lasthandoff: 02/24/2017

---
# <a name="chisquareddistribution-class"></a>chi_squared_distribution, classe
Génère une distribution suivant la loi unilatérale du Khi-deux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class RealType = double>  
class chi_squared_distribution {
public:    
    // types 
    typedef RealType result_type;    
    struct param_type;  

    // constructor and reset functions 
    explicit chi_squared_distribution(RealType n = 1);
    explicit chi_squared_distribution(const param_type& parm);
    void reset();  

    // generating functions 
    template <class URNG>  
    result_type operator()(URNG& gen);
    template <class URNG>
    result_type operator()(URNG& gen, const param_type& parm);
    
    // property functions 
    RealType n() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const;
};
```  
#### <a name="parameters"></a>Paramètres  
*RealType*  
Le type des résultats à virgule flottante est `double` par défaut. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).  
  
*URNG* Le moteur de génération de nombres aléatoires uniformes. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
La classe de modèle décrit une distribution qui produit des valeurs d’un type à virgule flottante spécifié par l’utilisateur, ou du type `double` si aucun n’est fourni, distribuées selon la loi du Khi-deux. Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[chi_squared_distribution::chi_squared_distribution](../standard-library/chi-squared-distribution-class.md)|`chi_squared_distribution::n`|`chi_squared_distribution::param`|  
|`chi_squared_distribution::operator()`||[chi_squared_distribution::param_type](#chi_squared_distribution__param_type)|  
  
La fonction de propriété `n()` retourne la valeur du paramètre de distribution stocké `n`.  
  
Le membre de propriété `param()` définit ou retourne le package de paramètres de distribution stocké `param_type`.  

Les fonctions membres `min()` et `max()` retournent respectivement le plus petit et le plus grand résultat possible.  
  
La fonction membre `reset()` ignore toutes les valeurs mises en cache. Ainsi, le résultat de l’appel suivant à `operator()` ne dépend d’aucune valeur obtenue à partir du moteur avant l’appel.  
  
Les fonctions membres `operator()` retournent la valeur générée suivante d’après le moteur URNG, à partir du package de paramètres actuel ou spécifié.
  
Pour plus d’informations sur les classes de distribution et leurs membres, consultez [\<random>](../standard-library/random.md).  
  
Pour plus d’informations sur la loi du Khi-deux, consultez l’article de Wolfram MathWorld [Chi-Squared Distribution](http://go.microsoft.com/fwlink/LinkId=400528).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double n, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::chi_squared_distribution<> distr(n);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "n() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.n() << std::endl;  
  
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
    double n_dist = 0.5;  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'n\' distribution parameter (must be greater than zero): ";  
    std::cin >> n_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(n_dist, samples);  
}  
```  
  
Première exécution :  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): .5  
Enter an integer value for the sample count: 10  
 
min() == 4.94066e-324  
max() == 1.79769e+308  
n() == 0.5000000000  
Distribution for 10 samples:  
    1: 0.0007625595  
    2: 0.0016895062  
    3: 0.0058683478  
    4: 0.0189647765  
    5: 0.0556619371  
    6: 0.1448191353  
    7: 0.1448245325  
    8: 0.1903494379  
    9: 0.9267525768  
    10: 1.5429743723  
```  
  
Deuxième exécution :  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): .3333  
Enter an integer value for the sample count: 10  
 
min() == 4.94066e-324  
max() == 1.79769e+308  
n() == 0.3333000000  
Distribution for 10 samples:  
    1: 0.0000148725  
    2: 0.0000490528  
    3: 0.0003175988  
    4: 0.0018454535  
    5: 0.0092808795  
    6: 0.0389540735  
    7: 0.0389562514  
    8: 0.0587028468  
    9: 0.6183666639  
    10: 1.3552086624  
```  
  
Troisième exécution :  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1000  
Enter an integer value for the sample count: 10  
 
min() == 4.94066e-324  
max() == 1.79769e+308  
n() == 1000.0000000000  
Distribution for 10 samples:  
    1: 958.5284624473  
    2: 958.7882787809  
    3: 963.0667684792  
    4: 987.9638091514  
    5: 1016.2433493745  
    6: 1021.9337111110  
    7: 1021.9723046240  
    8: 1035.7622110505  
    9: 1043.8725156645  
    10: 1054.7051509381  
```  
  
## <a name="requirements"></a>Spécifications  
**En-tête :** \<random>  
  
**Espace de noms :** std  
  
##  <a name="a-namechisquareddistributionchisquareddistributiona--chisquareddistributionchisquareddistribution"></a><a name="chi_squared_distribution__chi_squared_distribution"></a>  chi_squared_distribution::chi_squared_distribution  
Construit la distribution.  
  
```  
explicit chi_squared_distribution(result_type n = 1.0);  
explicit chi_squared_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Paramètres  
*n*  
Paramètre de distribution `n`.  
  
*parm*  
 Structure de paramètre utilisée pour construire la distribution.  
  
### <a name="remarks"></a>Notes  
**Condition préalable :** `0.0 < n`  
  
Le premier constructeur construit un objet dont la valeur `n` stockée contient la valeur *n*.  
  
Le deuxième constructeur construit un objet dont les paramètres stockés sont initialisés à partir de *parm*. Vous pouvez obtenir et définir les paramètres actuels d'une distribution existante en appelant la fonction membre `param()`.  
  
##  <a name="a-namechisquareddistributionparamtypea--chisquareddistributionparamtype"></a><a name="chi_squared_distribution__param_type"></a>  chi_squared_distribution::param_type  
Stocke les paramètres de la distribution.  
  
```cpp    
struct param_type {  
   typedef chi_squared_distribution<result_type> distribution_type;  
   param_type(result_type n = 1.0);
   result_type n() const;
   
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  

### <a name="parameters"></a>Paramètres  
*n*  
Paramètre de distribution `n`.  
  
*right*  
Objet `param_type` à comparer à this.  
  
### <a name="remarks"></a>Notes  
**Condition préalable :** `0.0 < n`  
  
Cette structure peut être passée au constructeur de classe de la distribution au moment de l'instanciation, à la fonction membre `param()` pour définir les paramètres stockés d'une distribution existante et à `operator()` pour une utilisation à la place des paramètres stockés.  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)




