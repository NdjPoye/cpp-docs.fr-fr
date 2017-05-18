---
title: linear_congruential_engine, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- linear_congruential_engine
- random/std::linear_congruential_engine
dev_langs:
- C++
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: 21
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
ms.openlocfilehash: bbb733e102af57627c00006816bb8d955877d0f8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="linearcongruentialengine-class"></a>linear_congruential_engine, classe
Génère une séquence aléatoire en utilisant l'algorithme congruentiel linéaire.  
  
## <a name="syntax"></a>Syntaxe  
```  
class linear_congruential_engine{  
   public:  // types  
   typedef UIntType result_type;  
   // engine characteristics  
   static constexpr result_type multiplier = a;  
   static constexpr result_type increment = c;  
   static constexpr result_type modulus = m;  
   static constexpr result_type min() { return c == 0u  1u: 0u; }  
   static constexpr result_type max() { return m - 1u; }  
   static constexpr result_type default_seed = 1u;  
   // constructors and seeding functions  
   explicit linear_congruential_engine(result_type s = default_seed);
   template <class Sseq>  
   explicit linear_congruential_engine(Sseq& q);
   void seed(result_type s = default_seed);
   template <class Sseq>  
   void seed(Sseq& q);
   // generating functions  
   result_type operator()();
   void discard(unsigned long long z);
   };  
```  
#### <a name="parameters"></a>Paramètres  
 `UIntType`  
 Type des résultats entiers non signés. Pour plus d’informations sur les types possibles, consultez [\<random>](../standard-library/random.md).  
  
 `A`  
 **Multiplier**. **Condition préalable** : consultez la section Notes.  
  
 `C`  
 **Increment**. **Condition préalable** : consultez la section Notes.  
  
 `M`  
 **Modulus**. **Condition préalable** : consultez la section Notes.  
  
## <a name="members"></a>Membres  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` est une constante membre, définie comme `1u`, utilisée comme valeur de paramètre par défaut pour `linear_congruential_engine::seed` et le constructeur de valeur unique.  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Remarques  
 La classe de modèle `linear_congruential_engine` est le moteur de générateur le plus simple, mais pas le plus rapide ni avec la qualité la plus élevée. [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md) est une version améliorée de ce moteur. Aucun de ces moteurs n’est aussi rapide ni ne produit des résultats d’aussi bonne qualité que [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Ce moteur produit des valeurs d’un type intégral non signé spécifié par l’utilisateur à l’aide de la relation de périodicité ( *period*) `x(i) = (A * x(i-1) + C) mod M`.  
  
 Si `M` est égal à zéro, la valeur utilisée pour cette opération de module est `numeric_limits<result_type>::max() + 1`. L'état du moteur est représenté par la dernière valeur retournée ou la valeur initiale si aucun appel n'a été passé à `operator()`.  
  
 Si `M` n'est pas égal à zéro, les valeurs des arguments de modèle `A` et `C` doivent être inférieures à `M`.  
  
 Bien que vous puissiez construire un générateur directement à partir de ce moteur, vous pouvez aussi utiliser l’un des typedefs prédéfinis suivants.  
  
 `minstd_rand0` : moteur standard minimal 1988 (Lewis, Goodman et Miller, 1969).  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand` : moteur standard minimal mis à jour `minstd_rand0` (Park, Miller et Stockmeyer, 1993).  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 Pour plus d’informations sur l’algorithme du moteur congruentiel linéaire, voir l’article de Wikipedia [Linear congruential generator](http://go.microsoft.com/fwlink/LinkId=402446).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)



