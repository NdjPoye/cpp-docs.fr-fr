---
title: subtract_with_carry_engine, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- subtract_with_carry_engine
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- subtract_with_carry_engine class
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: c73401963b231883d26aa45590a9cad305b13875
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="subtractwithcarryengine-class"></a>subtract_with_carry_engine, classe
Génère une séquence aléatoire en utilisant l'algorithme Substract With Carry (Lagged Fibonacci).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class UIntType, size_t W, size_t S, size_t R>  
class subtract_with_carry_engine;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `UIntType`  
 Type des résultats entiers non signés. Pour connaître les types possibles, consultez [\<random>](../standard-library/random.md).  
  
 `W`  
 **Taille de mot**. Taille de chaque mot, en bits, de la séquence d'état. **Condition préalable** : `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `S`  
 **Décalage court**. Nombre de valeurs entières. **Condition préalable** : `0 < S < R`  
  
 `R`  
 **Décalage long**. Détermine la périodicité dans la série générée.  
  
## <a name="members"></a>Membres  
  
||||  
|-|-|-|  
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|  
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|  
|`default_seed` est une constante membre, définie comme `19780503u`, utilisée comme valeur de paramètre par défaut pour `subtract_with_carry_engine::seed` et le constructeur de valeur unique.|||  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
 La classe de modèle `substract_with_carry_engine` est une version améliorée du [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md). Aucun de ces moteurs n’est aussi rapide ni ne produit des résultats d’aussi bonne qualité que [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Ce moteur produit des valeurs d’un type intégral non signé, spécifié par l’utilisateur, à l’aide de la relation de périodicité ( *période*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`, où `cy(i)` a la valeur `1` si `x(i - S) - x(i - R) - cy(i - 1) < 0`, sinon `0`, et `M` a la valeur `2`<sup>W</sup>. L'état du moteur est un indicateur de Carry plus `R` valeurs. Ces valeurs sont constituées des `R` dernières valeurs retournées si `operator()` a été appelé au moins `R` fois, sinon les `N` valeurs qui ont été retournées et les `R - N` dernières valeurs de la valeur initiale.  
  
 L'argument de modèle `UIntType` doit être assez volumineux pour contenir des valeurs jusqu'à `M - 1`.  
  
 Bien que vous puissiez construire un générateur directement à partir de ce moteur, vous pouvez aussi utiliser l’un des typedefs prédéfinis suivants :  
  
 `ranlux24_base` : utilisé comme base pour `ranlux24`.                   
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
 `ranlux48_base` : utilisé comme base pour `ranlux48`.                   
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
 Pour plus d’informations sur l’algorithme du moteur Substract With Carry, consultez l’article Wikipedia [Lagged Fibonacci generator](http://go.microsoft.com/fwlink/LinkId=402445).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)


