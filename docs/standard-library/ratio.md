---
title: "&lt;ratio&gt; | Microsoft Docs"
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
  - "ratio/std::mega"
  - "ratio/std::peta"
  - "ratio/std::ratio_greater"
  - "ratio/std::micro"
  - "ratio/std::ratio_add"
  - "ratio/std::ratio_not_equal"
  - "ratio/std::hecto"
  - "ratio/std::nano"
  - "ratio/std::ratio_less_equal"
  - "ratio/std::ratio_less"
  - "ratio/std::centi"
  - "ratio/std::ratio_greater_equal"
  - "ratio/std::ratio_subtract"
  - "<ratio>"
  - "ratio/std::atto"
  - "ratio/std::tera"
  - "ratio/std::milli"
  - "ratio/std::ratio_multiply"
  - "ratio/std::kilo"
  - "ratio/std::ratio_divide"
  - "ratio/std::giga"
  - "ratio/std::pico"
  - "ratio/std::femto"
  - "ratio/std::ratio_equal"
  - "ratio/std::ratio"
  - "ratio/std::exa"
  - "ratio/std::deci"
  - "ratio/std::deca"
dev_langs: 
  - "C++"
ms.assetid: 8543e912-2d84-45ea-b3c0-bd7bfacee405
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ratio&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez le rapport standard \<d'en\-tête\> pour définir les constantes et les modèles utilisés pour signaler et manipuler des nombres rationnels au moment de la compilation.  
  
## Syntaxe  
  
```cpp  
#include <ratio>  
```  
  
### structure de rapport  
  
```  
template <intmax_t N, intmax_t D = 1>  
struct ratio  
{  
    static constexpr intmax_t num;  
    static constexpr intmax_t den;  
    typedef ratio<num, den> type;  
};  
```  
  
 [ratio Structure](http://msdn.microsoft.com/fr-fr/3f7961f4-802b-4251-b3c3-090ef91c0dba) définit les constantes `num` statiques et `den` sorte que `num` \/\=\= d'`den` N\/D et `num` et `den` n'ont pas de facteur commun.  `num`\/`den` est `value` représenté par la classe de modèle.  Par conséquent, `type` indique l'instanciation `ratio<N0, D0>` pour laquelle \=\= N0 d'`num` et \=\= D0 d'`den`.  
  
### Spécialisations  
 \<le taux\> définit également les spécialisations d'`ratio` qui ont le format suivant.  
  
 `template <class R1, class R2> struct ratio_specialization`  
  
 Chaque spécialisation accepte deux paramètres du modèle qui doivent également être des spécialisations d'`ratio`.  La valeur d'`type` est déterminée par une opération logique associée.  
  
|Nom|Valeur `type`|  
|---------|-------------------|  
|`ratio_add`|`R1 + R2`|  
|`ratio_divide`|`R1 / R2`|  
|`ratio_equal`|`R1 == R2`|  
|`ratio_greater`|`R1 > R2`|  
|`ratio_greater_equal`|`R1 >= R2`|  
|`ratio_less`|`R1 < R2`|  
|`ratio_less_equal`|`R1 <= R2`|  
|`ratio_multiply`|`R1 * R2`|  
|`ratio_not_equal`|`!(R1 == R2)`|  
|`ratio_subtract`|`R1 - R2`|  
  
### typedefs  
  
```  
  
typedef ratio<1,        1000000000000000000> atto;  
typedef ratio<1,           1000000000000000> femto;  
typedef ratio<1,              1000000000000> pico;  
typedef ratio<1,                 1000000000> nano;  
typedef ratio<1,                    1000000> micro;  
typedef ratio<1,                       1000> milli;  
typedef ratio<1,                        100> centi;  
typedef ratio<1,                         10> deci;  
typedef ratio<                        10, 1> deca;  
typedef ratio<                       100, 1> hecto;  
typedef ratio<                      1000, 1> kilo;  
typedef ratio<                   1000000, 1> mega;  
typedef ratio<                1000000000, 1> giga;  
typedef ratio<             1000000000000, 1> tera;  
typedef ratio<          1000000000000000, 1> peta;  
typedef ratio<       1000000000000000000, 1> exa;  
  
```  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)