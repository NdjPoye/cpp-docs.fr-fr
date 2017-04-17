---
title: student_t_distribution, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- student_t_distribution
- std::student_t_distribution
- random/std::student_t_distribution
- random/std::student_t_distribution::result_type
- random/std::student_t_distribution::reset
- random/std::student_t_distribution::operator()
- random/std::student_t_distribution::n
- random/std::student_t_distribution::param
- random/std::student_t_distribution::min
- random/std::student_t_distribution::max
dev_langs:
- C++
helpviewer_keywords:
- student_t_distribution class
ms.assetid: 87b48127-9311-4d07-95df-833ed46bf0b1
caps.latest.revision: 16
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 61781e74ed9cc5424255b8697800000f8de5eb30
ms.lasthandoff: 02/24/2017

---
# <a name="studenttdistribution-class"></a>student_t_distribution, classe
Génère une distribution *T* de Student.  
  
## <a name="syntax"></a>Syntaxe  
```  
template<class RealType = double>
class student_t_distribution {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructor and reset functions  
   explicit student_t_distribution(result_type n = 1.0);
   explicit student_t_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type n() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
#### <a name="parameters"></a>Paramètres  
*RealType*  
 Le type des résultats à virgule flottante est `double` par défaut. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit une distribution qui produit des valeurs d’un type intégral spécifié par l’utilisateur, ou du type `double` si aucun type n’est fourni, distribuées selon la distribution *T* de Student. Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[student_t_distribution::student_t_distribution](#student_t_distribution__student_t_distribution)|`student_t_distribution::n`|`student_t_distribution::param`|  
|`student_t_distribution::operator()`||[student_t_distribution::param_type](#student_t_distribution__param_type)|  
  
 La fonction de propriété `n()` retourne la valeur du paramètre de distribution stocké `n`.  
  
 Pour plus d’informations sur les classes de distribution et leurs membres, consultez [\<random>](../standard-library/random.md).  
  
 Pour obtenir des informations détaillées sur la distribution *T* de Student, consultez l’article de Wolfram MathWorld sur la [distribution T de Student](http://go.microsoft.com/fwlink/LinkId=401094).  
  
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
  
    std::student_t_distribution<> distr(n);  
  
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
    std::cout << "Enter a floating point value for the 'n' distribution parameter (must be greater than zero): ";  
    std::cin >> n_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(n_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
n() == 1.0000000000  
Distribution for 10 samples:  
    1: -1.3084956212  
    2: -1.0899518684  
    3: -0.9568771388  
    4: -0.9372088821  
    5: -0.7381334669  
    6: -0.2488074854  
    7: -0.2028714601  
    8: 1.4013074495  
    9: 5.3244792236  
    10: 92.7084335614  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
##  <a name="a-namestudenttdistributionstudenttdistributiona--studenttdistributionstudenttdistribution"></a><a name="student_t_distribution__student_t_distribution"></a>  student_t_distribution::student_t_distribution  
 Construit la distribution.  
  
```  
explicit student_t_distribution(RealType n = 1.0);
explicit student_t_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Paramètres  
*n*  
 Paramètre de distribution `n`.  
  
*parm*  
 Package de paramètres utilisé pour construire la distribution.  
  
### <a name="remarks"></a>Notes  
 **Condition préalable :** `0.0 < n`  
  
 Le premier constructeur construit un objet dont la valeur `n` stockée contient la valeur *n*.  
  
 Le deuxième constructeur construit un objet dont les paramètres stockés sont initialisés à partir de *parm*. Vous pouvez obtenir et définir les paramètres actuels d'une distribution existante en appelant la fonction membre `param()`.  
  
##  <a name="a-namestudenttdistributionparamtypea--studenttdistributionparamtype"></a><a name="student_t_distribution__param_type"></a>  student_t_distribution::param_type  
 Stocke tous les paramètres de la distribution.  
```cpp    
struct param_type {  
   typedef student_t_distribution<result_type> distribution_type;  
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



