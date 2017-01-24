---
title: "piecewise_linear_distribution, classe | Microsoft Docs"
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
  - "std::tr1::piecewise_linear_distribution"
  - "tr1.piecewise_linear_distribution"
  - "piecewise_linear_distribution"
  - "std.tr1.piecewise_linear_distribution"
  - "random/std::tr1::piecewise_linear_distribution"
  - "tr1::piecewise_linear_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "piecewise_linear_distribution (classe)"
ms.assetid: cd141152-7163-4754-8f98-c6d6500005e0
caps.latest.revision: 21
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# piecewise_linear_distribution, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une distribution linéaire par morceaux qui présente des intervalles de largeur variable avec une probabilité variable linéairement dans chaque intervalle.  
  
## Syntaxe  
  
```  
template<class RealType = double>  
class piecewise_linear_distribution  
{  
public:  
    // types  
    typedef RealType result_type;  
    struct param_type;  
    // constructor and reset functions  
    piecewise_linear_distribution();  
    template<class InputIteratorI, class InputIteratorW>  
    piecewise_linear_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);  
    template<class UnaryOperation>  
    piecewise_linear_distribution(initializer_list<RealType> intervals, UnaryOperation weightfunc);  
    template<class UnaryOperation>  
    piecewise_linear_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);  
    explicit piecewise_linear_distribution(const param_type& parm);  
    void reset();  
    // generating functions  
    template<class URNG>  
    result_type operator()(URNG& gen);  
    template<class URNG>  
    result_type operator()(URNG& gen, const param_type& parm);  
    // property functions  
    vector<result_type> intervals() const;  
    vector<result_type> densities() const;  
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
 Cette distribution d'échantillonnage présente des intervalles de largeur variable avec une probabilité variable linéairement dans chaque intervalle. Pour plus d'informations sur d'autres distributions d'échantillonnages, voir [piecewise\_constant\_distribution](../standard-library/piecewise-constant-distribution-class.md) et [discrete\_distribution](../standard-library/discrete-distribution-class.md).  
  
 Le tableau suivant contient des liens vers des articles sur différents membres :  
  
||||  
|-|-|-|  
|[piecewise\_linear\_distribution::piecewise\_linear\_distribution](../Topic/piecewise_linear_distribution::piecewise_linear_distribution.md)|`piecewise_linear_distribution::intervals`|`piecewise_linear_distribution::param`|  
|`piecewise_linear_distribution::operator()`|`piecewise_linear_distribution::densities`|[piecewise\_linear\_distribution::param\_type](../Topic/piecewise_linear_distribution::param_type.md)|  
  
 La fonction de propriété `intervals()` retourne un `vector<RealType>` avec l'ensemble d'intervalles stockés de la distribution.  
  
 La fonction de propriété `densities()` retourne un `vector<RealType>` avec les densités stockées pour chaque ensemble d'intervalles, qui sont calculées en fonction des poids fournis dans les paramètres du constructeur.  
  
 Pour plus d’informations sur les classes de distribution et leurs membres, consultez la page [\<random\>](../standard-library/random.md).  
  
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
  
    // Three intervals, non-uniform: 0 to 1, 1 to 6, and 6 to 15  
    vector<double> intervals{ 0, 1, 6, 15 };  
    // weights determine the densities used by the distribution  
    vector<double> weights{ 1, 5, 5, 10 };  
  
    piecewise_linear_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "intervals (index: interval):" << endl;  
    vector<double> i = distr.intervals();  
    int counter = 0;  
    for (const auto& n : i) {  
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;  
        ++counter;  
    }  
    cout << endl;  
    cout << "densities (index: density):" << endl;  
    vector<double> d = distr.densities();  
    counter = 0;  
    for (const auto& n : d) {  
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
        cout << setw(5) << elem.first << '-' << elem.first + 1 << ' ' << string(elem.second, ':') << endl;  
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
  
```Output  
Utilisez CTRL + Z pour ignorer l’entrée des données et exécuter à l’aide des valeurs par défaut. Entrez une valeur entière pour le nombre d’échantillons : 100min() == 0max() == 15intervals (index : intervalle) : 0 : 0,0000000000 1 : 1,0000000000 2 : 6.0000000000 3 : 15.0000000000densities (index : densité) : 0 : 0.0645161290 1 : 0.3225806452 2 : 0.3225806452 3 : 0.6451612903Distribution pour 100 échantillons : 0-1 ::: 1-2 ::: 2-3 ::: 3-4 ::: 4-5 ::: 5 et 6 ::: 6-7 ::: 7-8 ::: 8-9 ::: 9 et 10 ::: 10 et 11 ::: 11-12 : 12 et 13 ::: 13 et 14 ::: 14 et 15 :::  
```  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)