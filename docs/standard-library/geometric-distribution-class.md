---
title: "geometric_distribution, classe | Microsoft Docs"
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
  - "std.tr1.geometric_distribution"
  - "random/std::tr1::geometric_distribution"
  - "tr1::geometric_distribution"
  - "tr1.geometric_distribution"
  - "geometric_distribution"
  - "std::tr1::geometric_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "geometric_distribution (classe)"
  - "geometric_distribution (classe) (TR1)"
ms.assetid: 38f933af-3b49-492e-9d26-b6b272a60013
caps.latest.revision: 24
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# geometric_distribution, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une distribution géométrique.  
  
## Syntaxe  
  
```  
template<class IntType = int> class geometric_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit geometric_distribution(double p = 0.5);     explicit geometric_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     double p() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Paramètres  
 `IntType`  
 Le type des résultats entiers est `int` par défaut.  Pour plus d'informations sur les types possibles, consultez [\<random\>](../standard-library/random.md).  
  
## Notes  
 La classe de modèle décrit une distribution qui produit des valeurs d'un type intégral spécifié par l'utilisateur avec une distribution géométrique.  Le tableau suivant contient des liens vers des articles sur différents membres.  
  
||||  
|-|-|-|  
|[geometric\_distribution::geometric\_distribution](../Topic/geometric_distribution::geometric_distribution.md)|`geometric_distribution::p`|`geometric_distribution::param`|  
|`geometric_distribution::operator()`||[geometric\_distribution::param\_type](../Topic/geometric_distribution::param_type.md)|  
  
 La fonction de propriété `p()` retourne la valeur du paramètre de distribution stocké `p`.  
  
 Pour plus d'informations sur les classes de distribution et leurs membres, consultez [\<random\>](../standard-library/random.md).  
  
 Pour plus d'informations sur la distribution suivant la loi unilatérale du Khi\-deux, consultez l'article de Wolfram MathWorld sur la [distribution géométrique](http://go.microsoft.com/fwlink/?LinkId=400529).  
  
## Exemple  
  
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
  
    std::geometric_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.p() << std::endl;  
  
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
    double p_dist = 0.5;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'p\' distribution parameter: ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
## Sortie  
 Premier test :  
  
  **Utilisez Ctrl\+Z pour ignorer l'entrée des données et procéder à l'exécution à l'aide des valeurs par défaut.  Entrez une valeur à virgule flottante pour le paramètre de distribution 'p' : 0,5**  
**Entrez une valeur entière pour le nombre d'échantillons : 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 0.5000000000**  
**Distribution pour 100 échantillons :**  
 **0 ::::::::::::::::::::::::::::::::::::::::::::::::::::**  
 **1 ::::::::::::::::::::::::**  
 **2 ::::::::::::::**  
 **3 :::::**  
 **4 ::**  
 **5 ::**  
 **6 :**  Second test :  
  
  **Utilisez Ctrl\+Z pour ignorer l'entrée des données et procéder à l'exécution à l'aide des valeurs par défaut.  Entrez une valeur à virgule flottante pour le paramètre de distribution 'p' : 0,1**  
**Entrez une valeur entière pour le nombre d'échantillons : 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 0.1000000000**  
**Distribution pour 100 échantillons :**  
 **0 :::::::::**  
 **1 :::::::::::**  
 **2 :::::::**  
 **3 ::::::::**  
 **4 ::::::::**  
 **5 ::::::**  
 **6 :::::**  
 **7 ::::::**  
 **8 :::::**  
 **9 ::::**  
 **10 ::::**  
 **11 ::**  
 **12 :**  
 **13 :**  
 **14 :::**  
 **15 ::::**  
 **16 :::**  
 **17 :**  
 **18 :**  
 **19 :**  
 **20 ::**  
 **21 :**  
 **22 :**  
 **23 :**  
 **28 ::**  
 **33 :**  
 **35 :**  
 **40 :**    
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)