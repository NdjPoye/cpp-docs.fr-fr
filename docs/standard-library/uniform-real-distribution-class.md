---
title: "uniform_real_distribution, classe | Microsoft Docs"
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
  - "tr1::uniform_real_distribution"
  - "std::tr1::uniform_real_distribution"
  - "random/std::tr1::uniform_real_distribution"
  - "uniform_real_distribution"
  - "std.tr1.uniform_real_distribution"
  - "tr1.uniform_real_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uniform_real_distribution (classe)"
ms.assetid: 5cf906fd-0319-4984-b21b-98425cd7532d
caps.latest.revision: 18
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# uniform_real_distribution, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une distribution à virgule flottante uniforme \(toutes les valeurs ont le même degré de probabilité\) dans une plage de sortie qui est inclusive\-exclusive.  
  
## Syntaxe  
  
```  
template<class RealType = double> class uniform_real_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructors and reset functions     explicit uniform_real_distribution(RealType a = 0.0, RealType b = 1.0);     explicit uniform_real_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     result_type a() const;     result_type b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Paramètres  
 `RealType`  
 Le type des résultats à virgule flottante est `double` par défaut.  Pour plus d'informations sur les types possibles, voir [\<random\>](../standard-library/random.md).  
  
## Notes  
 La classe de modèle décrit une distribution inclusive\-exclusive qui produit des valeurs d'un type à virgule flottante intégral spécifié par l'utilisateur avec une distribution pour que toutes les valeurs aient le même degré de probabilité.  Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[uniform\_real\_distribution::uniform\_real\_distribution](../Topic/uniform_real_distribution::uniform_real_distribution.md)|`uniform_real_distribution::a`|`uniform_real_distribution::param`|  
|`uniform_real_distribution::operator()`|`uniform_real_distribution::b`|[uniform\_real\_distribution::param\_type](../Topic/uniform_real_distribution::param_type.md)|  
  
 Le membre de propriété `a()` retourne la limite minimale de la distribution stockée actuellement, tandis que `b()` retourne la limite maximale stockée actuellement.  Pour cette classe de distribution, ces valeurs minimales et maximales sont les mêmes que celles retournées par les fonctions de propriété courantes `min()` et `max()` décrites dans la rubrique [\<random\>](../standard-library/random.md).  
  
 Pour plus d'informations sur les classes de distribution et leurs membres, voir [\<random\>](../standard-library/random.md).  
  
## Exemple  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::uniform_real_distribution<> distr(a,b);  
  
    std::cout << "lower bound == " << distr.a() << std::endl;  
    std::cout << "upper bound == " << distr.b() << std::endl;  
  
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
            << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 1.0;  
    double b_dist = 1.5;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the lower bound of the distribution: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the upper bound of the distribution: ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## Sortie  
  **Utilisez Ctrl\+Z pour ignorer l'entrée des données et procéder à l'exécution à l'aide des valeurs par défaut.  Entrez une valeur à virgule flottante pour la limite inférieure de la distribution : 0,5**  
**Entrez une valeur à virgule flottante pour la limite supérieure de la distribution : 1**  
**Entrez une valeur entière pour le nombre d'échantillons : 20**  
**limite inférieure \=\= 0,5**  
**limite supérieure \=\= 1**  
**Distribution pour 20 échantillons :**  
 **1: 0.5144304741**  
 **2: 0.6003997192**  
 **3: 0.6060792968**  
 **4: 0.6270416650**  
 **5: 0.6295091197**  
 **6: 0.6437749373**  
 **7: 0.6513740058**  
 **8: 0.7062379346**  
 **9: 0.7117609406**  
 **10: 0.7206888566**  
 **11: 0.7423223702**  
 **12: 0.7826033033**  
 **13: 0.8112872958**  
 **14: 0.8440467608**  
 **15: 0.8461254641**  
 **16: 0.8598305065**  
 **17: 0.8640874069**  
 **18: 0.8770968361**  
 **19: 0.9397858282**  
 **20: 0.9804645012**    
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)