---
title: "student_t_distribution, classe | Microsoft Docs"
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
  - "std::tr1::student_t_distribution"
  - "tr1::student_t_distribution"
  - "std.tr1.student_t_distribution"
  - "random/std::tr1::student_t_distribution"
  - "tr1.student_t_distribution"
  - "student_t_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "student_t_distribution (classe)"
ms.assetid: 87b48127-9311-4d07-95df-833ed46bf0b1
caps.latest.revision: 16
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# student_t_distribution, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une distribution de Student.  
  
## Syntaxe  
  
```  
template<class RealType = double>  
class student_t_distribution  
{  
public:  
    // types  
    typedef RealType result_type;  
    struct param_type;  
    // constructor and reset functions  
    explicit student_t_distribution(RealType n = 1.0);  
    explicit student_t_distribution(const param_type& parm);  
    void reset();  
    // generating functions  
    template<class URNG>  
    result_type operator()(URNG& gen);  
    template<class URNG>  
    result_type operator()(URNG& gen, const param_type& parm);  
    // property functions  
    RealType n() const;  
    param_type param() const;  
    void param(const param_type& parm);  
    result_type min() const;  
    result_type max() const;  
};  
```  
  
#### Paramètres  
 `RealType`  
 Le type des résultats à virgule flottante est `double` par défaut. Pour les types possibles, consultez la page [\<random\>](../standard-library/random.md).  
  
## Notes  
 La classe de modèle décrit une distribution qui produit des valeurs d'un type intégral spécifié par l'utilisateur, ou du type `double` si aucun n'est fourni, distribuées selon la loi de Student. Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[student\_t\_distribution::student\_t\_distribution](../Topic/student_t_distribution::student_t_distribution.md)|`student_t_distribution::n`|`student_t_distribution::param`|  
|`student_t_distribution::operator()`||[student\_t\_distribution::param\_type](../Topic/student_t_distribution::param_type.md)|  
  
 La fonction de propriété `n()` retourne la valeur du paramètre de distribution stocké `n`.  
  
 Pour plus d’informations sur les classes de distribution et leurs membres, consultez la page [\<random\>](../standard-library/random.md).  
  
 Pour plus d’informations sur la loi de Student *t*\-distribution, consultez l’article de Wolfram mathworld [t\-Distribution de Student](http://go.microsoft.com/fwlink/?LinkId=401094).  
  
## Exemple  
  
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
  
## Sortie  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
  
min() == -1.79769e+308  
max() == 1.79769e+308  
n() == 1.0000000000  
Distribution for 10 samples:  
          1:  -1.3084956212  
          2:  -1.0899518684  
          3:  -0.9568771388  
          4:  -0.9372088821  
          5:  -0.7381334669  
          6:  -0.2488074854  
          7:  -0.2028714601  
          8:   1.4013074495  
          9:   5.3244792236  
         10:  92.7084335614  
```  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)