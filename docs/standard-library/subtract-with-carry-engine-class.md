---
title: "subtract_with_carry_engine, classe | Microsoft Docs"
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
  - "tr1.subtract_with_carry_engine"
  - "std::tr1::subtract_with_carry_engine"
  - "random/std::tr1::subtract_with_carry_engine"
  - "subtract_with_carry_engine"
  - "tr1::subtract_with_carry_engine"
  - "std.tr1.subtract_with_carry_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "subtract_with_carry_engine (classe)"
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
caps.latest.revision: 20
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# subtract_with_carry_engine, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire en utilisant l'algorithme Substract With Carry \(Lagged Fibonacci\).  
  
## Syntaxe  
  
```  
template<class UIntType, size_t W, size_t S, size_t R>  
class subtract_with_carry_engine;  
```  
  
#### Paramètres  
 `UIntType`  
 Type des résultats entiers non signés. Pour les types possibles, consultez la page [\<random\>](../standard-library/random.md).  
  
 `W`  
 **Taille de mot**. Taille de chaque mot, en bits, de la séquence d'état.**Condition préalable** : `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `S`  
 **Décalage court**. Nombre de valeurs entières.**Condition préalable** : `0 < S < R`  
  
 `R`  
 **Décalage long**. Détermine la périodicité dans la série générée.  
  
## Membres  
  
||||  
|-|-|-|  
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|  
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|  
|`default_seed` est une constante membre, définie comme `19780503u`, utilisée comme valeur de paramètre par défaut pour `subtract_with_carry_engine::seed` et le constructeur de valeur unique.|||  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random\>](../standard-library/random.md).  
  
## Notes  
 La classe de modèle `substract_with_carry_engine` est une version améliorée du [linear\_congruential\_engine](../standard-library/linear-congruential-engine-class.md). Aucun de ces moteurs n'est aussi rapide ni ne produit des résultats d'aussi bonne qualité que [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Ce moteur produit des valeurs d'un type intégral non signé spécifié par l'utilisateur à l'aide de la relation de périodicité \(*période*\) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`, où `cy(i)` a la valeur `1` si `x(i - S) - x(i - R) - cy(i - 1) < 0`, sinon `0`, et `M` a la valeur `2`<sup>W</sup>. L'état du moteur est un indicateur de Carry plus `R` valeurs. Ces valeurs sont constituées des `R` dernières valeurs retournées si `operator()` a été appelé au moins `R` fois, sinon les `N` valeurs qui ont été retournées et les `R - N` dernières valeurs de la valeur initiale.  
  
 L'argument de modèle `UIntType` doit être assez volumineux pour contenir des valeurs jusqu'à `M - 1`.  
  
 Bien que vous puissiez construire un générateur à partir de ce moteur directement, vous pouvez également utiliser une de ces typedefs prédéfinis :  
  
 `ranlux24_base`: Utilisé comme base pour `ranlux24`.  
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
 `ranlux48_base`: Utilisé comme base pour `ranlux48`.  
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
 Pour plus d’informations sur l’algorithme substract with carry moteur, voir l’article de Wikipedia [Lagged Fibonacci generator](http://go.microsoft.com/fwlink/?LinkId=402445).  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)