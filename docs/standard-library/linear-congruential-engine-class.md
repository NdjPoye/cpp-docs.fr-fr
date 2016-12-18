---
title: "linear_congruential_engine, classe | Microsoft Docs"
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
  - "std.tr1.linear_congruential_engine"
  - "random/std::tr1::linear_congruential_engine"
  - "linear_congruential_engine"
  - "std::tr1::linear_congruential_engine"
  - "tr1.linear_congruential_engine"
  - "tr1::linear_congruential_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "linear_congruential_engine (classe)"
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: 21
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# linear_congruential_engine, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire en utilisant l'algorithme congruentiel linéaire.  
  
## Syntaxe  
  
```  
template<class UIntType, UIntType A, UIntType C, UIntType M>  
class linear_congruential_engine{  
public:  
    // types  
    typedef UIntType result_type;  
  
    // engine characteristics  
    static constexpr result_type multiplier = a;  
    static constexpr result_type increment = c;  
    static constexpr result_type modulus = m;  
    static constexpr result_type min() { return c == 0u ? 1u: 0u; }  
    static constexpr result_type max() { return m - 1u; }  
    static constexpr result_type default_seed = 1u;  
  
    // constructors and seeding functions  
    explicit linear_congruential_engine(result_type s = default_seed);  
    template<class Sseq> explicit linear_congruential_engine(Sseq& q);  
    void seed(result_type s = default_seed);  
    template<class Sseq> void seed(Sseq& q);  
  
    // generating functions  
    result_type operator()();  
    void discard(unsigned long long z);  
};  
```  
  
#### Paramètres  
 `UIntType`  
 Type des résultats entiers non signés. Pour les types possibles, consultez la page [\<random\>](../standard-library/random.md).  
  
 `A`  
 **Multiplicateur**.**Condition préalable** : consultez la section Notes.  
  
 `C`  
 **Incrémentation**.**Condition préalable** : consultez la section Notes.  
  
 `M`  
 **Module**.**Condition préalable** : consultez la section Notes.  
  
## Membres  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` est une constante membre, définie comme `1u`, utilisée comme valeur de paramètre par défaut pour `linear_congruential_engine::seed` et le constructeur de valeur unique.  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random\>](../standard-library/random.md).  
  
## Notes  
 La classe de modèle `linear_congruential_engine` est le moteur de générateur le plus simple, mais pas le plus rapide ni avec la qualité la plus élevée. Une version améliorée de ce moteur est [substract\_with\_carry\_engine](../standard-library/subtract-with-carry-engine-class.md). Aucun de ces moteurs n'est aussi rapide ni ne produit des résultats d'aussi bonne qualité que [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Ce moteur produit des valeurs d'un type intégral non signé spécifié par l'utilisateur à l'aide de la relation de périodicité \(*période*\) `x(i) = (A * x(i-1) + C) mod M`.  
  
 Si `M` est égal à zéro, la valeur utilisée pour cette opération de module est `numeric_limits<result_type>::max() + 1`. L'état du moteur est représenté par la dernière valeur retournée ou la valeur initiale si aucun appel n'a été passé à `operator()`.  
  
 Si `M` n'est pas égal à zéro, les valeurs des arguments de modèle `A` et `C` doivent être inférieures à `M`.  
  
 Bien que vous puissiez construire un générateur à partir de ce moteur directement, vous pouvez également utiliser une de ces typedefs prédéfinis.  
  
 `minstd_rand0`: moteur standard minimal 1988 \(Lewis, Goodman et Miller, 1969\).  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand`: Mise à jour de moteur standard minimal `minstd_rand0` \(Park, Miller et Stockmeyer, 1993\).  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 Pour plus d’informations sur l’algorithme du moteur congruentiel linéaire, consultez l’article de Wikipedia [Générateur congruentiel linéaire](http://go.microsoft.com/fwlink/?LinkId=402446).  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)