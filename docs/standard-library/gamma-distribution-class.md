---
title: gamma_distribution, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::gamma_distribution
- random/std::gamma_distribution::reset
- random/std::gamma_distribution::alpha
- random/std::gamma_distribution::beta
- random/std::gamma_distribution::param
- random/std::gamma_distribution::min
- random/std::gamma_distribution::max
- random/std::gamma_distribution::operator()
- random/std::gamma_distribution::param_type
- random/std::gamma_distribution::param_type::alpha
- random/std::gamma_distribution::param_type::beta
- random/std::gamma_distribution::param_type::operator==
- random/std::gamma_distribution::param_type::operator!=
- random/std::gamma_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- std::gamma_distribution [C++]
- std::gamma_distribution [C++], reset
- std::gamma_distribution [C++], alpha
- std::gamma_distribution [C++], beta
- std::gamma_distribution [C++], param
- std::gamma_distribution [C++], min
- std::gamma_distribution [C++], max
- std::gamma_distribution [C++], param_type
- std::gamma_distribution [C++], param_type
ms.assetid: 2a6798ac-6152-41d7-8ef6-d684d92f1572
caps.latest.revision: 18
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 048f1956d84837512a3273eeae089d6ffef00ced
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="gammadistribution-class"></a>gamma_distribution, classe
Génère une distribution Gamma.  
  
## <a name="syntax"></a>Syntaxe  
```  
template<class RealType = double>
class gamma_distribution {
public:    
    // types 
    typedef RealType result_type;    
    struct param_type;  

    // constructors and reset functions 
    explicit gamma_distribution(result_type alpha = 1.0, result_type beta = 1.0);
    explicit gamma_distribution(const param_type& parm);
    void reset();
    
    // generating functions
    template <class URNG>  
    result_type operator()(URNG& gen);
    template <class URNG>
    result_type operator()(URNG& gen, const param_type& parm);
    
    // property functions
    result_type alpha() const;
    result_type beta() const;
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
La classe de modèle décrit une distribution qui produit des valeurs d’un type à virgule flottante spécifié par l’utilisateur, ou du type `double` si aucun n’est fourni, distribuées selon la loi Gamma. Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[gamma_distribution](#gamma_distribution)|`gamma_distribution::alpha`|`gamma_distribution::param`|  
|`gamma_distribution::operator()`|`gamma_distribution::beta`|[param_type](#param_type)|  
  
Les fonctions de propriété `alpha()` et `beta()` retournent leurs valeurs respectives pour les paramètres de distribution stockés *alpha* et *beta*.  
  
Le membre de propriété `param()` définit ou retourne le package de paramètres de distribution stocké `param_type`.  

Les fonctions membres `min()` et `max()` retournent respectivement le plus petit et le plus grand résultat possible.  
  
La fonction membre `reset()` ignore toutes les valeurs mises en cache. Ainsi, le résultat de l’appel suivant à `operator()` ne dépend d’aucune valeur obtenue à partir du moteur avant l’appel.  
  
Les fonctions membres `operator()` retournent la valeur générée suivante d’après le moteur URNG, à partir du package de paramètres actuel ou spécifié.
  
Pour plus d’informations sur les classes de distribution et leurs membres, consultez [\<random>](../standard-library/random.md).  
  
Pour plus d’informations sur la loi de Gamma, consultez l’article de Wolfram MathWorld [Gamma Distribution](http://go.microsoft.com/fwlink/LinkId=401111).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::gamma_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "alpha() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.alpha() << std::endl;  
    std::cout << "beta() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.beta() << std::endl;  
  
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
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): 1  
Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == 4.94066e-324  
max() == 1.79769e+308  
alpha() == 1.0000000000  
beta() == 1.0000000000  
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
  
##  <a name="gamma_distribution"></a>  gamma_distribution::gamma_distribution  
Construit la distribution.  
  
```  
explicit gamma_distribution(result_type alpha = 1.0, result_type beta = 1.0);
explicit gamma_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Paramètres  
*alpha*  
Paramètre de distribution `alpha`.  
  
*beta*  
Paramètre de distribution `beta`.  
  
*parm*  
Structure de paramètre utilisée pour construire la distribution.  
  
### <a name="remarks"></a>Notes  
**Condition préalable :** `0.0 < alpha` et `0.0 < beta`  
  
Le premier constructeur construit un objet dont la valeur `alpha` stockée contient la valeur *alpha* et dont la valeur `beta` stockée contient la valeur *beta*.  
  
Le deuxième constructeur construit un objet dont les paramètres stockés sont initialisés à partir de *parm*. Vous pouvez obtenir et définir les paramètres actuels d'une distribution existante en appelant la fonction membre `param()`.  
  
##  <a name="param_type"></a>  gamma_distribution::param_type  
Stocke les paramètres de la distribution.  
  
```cpp   
struct param_type {  
   typedef gamma_distribution<result_type> distribution_type;  
   param_type(result_type alpha = 1.0, result_type beta 1.0);
   result_type alpha() const;
   result_type beta() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
### <a name="parameters"></a>Paramètres  
*alpha*  
Paramètre de distribution `alpha`.  
  
*beta*  
Paramètre de distribution `beta`.  
  
*right*  
Instance `param_type` à comparer.  
  
### <a name="remarks"></a>Notes  
**Condition préalable :** `0.0 < alpha` et `0.0 < beta`  
  
Cette structure peut être passée au constructeur de classe de la distribution au moment de l'instanciation, à la fonction membre `param()` pour définir les paramètres stockés d'une distribution existante et à `operator()` pour une utilisation à la place des paramètres stockés.  
  
## <a name="see-also"></a>Voir aussi  
[\<random>](../standard-library/random.md)




