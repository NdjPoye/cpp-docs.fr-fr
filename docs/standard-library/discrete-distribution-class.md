---
title: "discrete_distribution, classe | Microsoft Docs"
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
  - "random/std::tr1::discrete_distribution"
  - "std::tr1::discrete_distribution"
  - "tr1.discrete_distribution"
  - "std.tr1.discrete_distribution"
  - "discrete_distribution"
  - "tr1::discrete_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "discrete_distribution (classe)"
ms.assetid: 8c8ba8f8-c06f-4f07-b354-f53950142fcf
caps.latest.revision: 21
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# discrete_distribution, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une distribution d'entiers discrète qui présente des intervalles de largeur uniforme avec une probabilité uniforme dans chaque intervalle.  
  
## Syntaxe  
  
```  
template<class IntType = int> class discrete_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructor and reset functions     discrete_distribution();     template<class InputIterator>     discrete_distribution(InputIterator firstW, InputIterator lastW);     discrete_distribution(initializer_list<double> weightlist);     template<class UnaryOperation>     discrete_distribution(size_t count, double xmin, double xmax, UnaryOperation funcweight);     explicit discrete_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     vector<double> probabilities() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Paramètres  
 `IntType`  
 Le type des résultats entiers est `int` par défaut.  Pour plus d'informations sur les types possibles, voir [\<random\>](../standard-library/random.md).  
  
## Notes  
 Cette distribution d'échantillonnage présente des intervalles de largeur uniforme avec une probabilité uniforme dans chaque intervalle.  Pour plus d'informations sur d'autres distributions d'échantillonnages, voir [piecewise\_linear\_distribution, classe](../standard-library/piecewise-linear-distribution-class.md) et [piecewise\_constant\_distribution, classe](../standard-library/piecewise-constant-distribution-class.md).  
  
 Le tableau suivant contient des liens vers des articles sur différents membres :  
  
|||  
|-|-|  
|[discrete\_distribution::discrete\_distribution](../Topic/discrete_distribution::discrete_distribution.md)|`discrete_distribution::param`|  
|`discrete_distribution::operator()`|[discrete\_distribution::param\_type](../Topic/discrete_distribution::param_type.md)|  
  
 La fonction de propriété `vector<double> probabilities()` retourne les probabilités individuelles pour chaque entier généré.  
  
 Pour plus d'informations sur les classes de distribution et leurs membres, voir [\<random\>](../standard-library/random.md).  
  
## Exemple  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
using namespace std;  
  
void test(const int s) {  
  
    // uncomment to use a non-deterministic generator  
    // random_device rd;  
    // mt19937 gen(rd());  
    mt19937 gen(1701);  
  
    discrete_distribution<> distr({ 1, 2, 3, 4, 5 });  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "probabilities (value: probability):" << endl;  
    vector<double> p = distr.probabilities();  
    int counter = 0;  
    for (const auto& n : p) {  
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;  
        ++counter;  
    }  
    cout << endl;  
  
    // generate the distribution as a histogram  
    map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    cout << "Distribution for " << s << " samples:" << endl;  
    for (const auto& elem : histogram) {  
        cout << setw(5) << elem.first << ' ' << string(elem.second, ':') << endl;  
    }  
    cout << endl;  
}  
  
int main()  
{  
    int samples = 100;  
  
    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;  
    cout << "Enter an integer value for the sample count: ";  
    cin >> samples;  
  
    test(samples);  
}  
  
```  
  
## Sortie  
  **Utilisez Ctrl\+Z pour ignorer l'entrée des données et procéder à l'exécution à l'aide des valeurs par défaut.  Entrez une valeur entière pour le nombre d'échantillons : 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 4**  
**probabilités \(valeur : probabilité\) :**  
 **0:   0.0666666667**  
 **1:   0.1333333333**  
 **2:   0.2000000000**  
 **3:   0.2666666667**  
 **4:   0.3333333333**  
**Distribution pour 100 échantillons :**  
 **0 :::::**  
 **1 ::::::::::::::**  
 **2 :::::::::::::::::**  
 **3 ::::::::::::::::::::::::::::::**  
 **4 ::::::::::::::::::::::::::::::::::**    
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)