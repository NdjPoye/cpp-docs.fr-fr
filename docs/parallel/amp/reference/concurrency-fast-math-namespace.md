---
title: Concurrency::fast_math Namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d8a94b0911b772f4972416722757bec24a4826ed
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math, espace de noms
Les fonctions dans les `fast_math` espace de noms ont une précision inférieure, prennent en charge uniquement simple précision (`float`) et appeler les fonctions intrinsèques de DirectX. Il existe deux versions de chaque fonction, par exemple `cos` et `cosf`. Les deux versions acceptent et retournent un `float`, mais chaque appelle la même DirectX intrinsèque.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Calcule l’arc cosinus de l’argument|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Calcule l’arc cosinus de l’argument|  
|[asin](concurrency-fast-math-namespace-functions.md#asin)|Calcule l’arc sinus de l’argument|  
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Calcule l’arc sinus de l’argument|  
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Calcule l’arc tangente de l’argument|  
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|Calcule l’arc tangente de _Y/_X|  
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|Calcule l’arc tangente de _Y/_X|  
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Calcule l’arc tangente de l’argument|  
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Calcule le plafond de l’argument|  
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Calcule le plafond de l’argument|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Calcule le cosinus de l’argument|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Calcule le cosinus de l’argument|  
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|Calcule la valeur de cosinus hyperbolique de l’argument|  
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Calcule la valeur de cosinus hyperbolique de l’argument|  
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Calcule la valeur exponentielle de l’argument de base e|  
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|Calcule la valeur exponentielle de l’argument base-2|  
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Calcule la valeur exponentielle de l’argument base-2|  
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Calcule la valeur exponentielle de l’argument de base e|  
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Retourne la valeur absolue de l’argument|  
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Retourne la valeur absolue de l’argument|  
|[floor](concurrency-fast-math-namespace-functions.md#floor)|Calcule le plancher de l’argument|  
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Calcule le plancher de l’argument|  
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Déterminer la valeur numérique maximale des arguments|  
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Déterminer la valeur numérique maximale des arguments|  
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Déterminer la valeur numérique minimale des arguments|  
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Déterminer la valeur numérique minimale des arguments|  
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Calcule le reste à virgule flottante de _X/_Y|  
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Calcule le reste à virgule flottante de _X/_Y|  
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Obtient la mantisse et l’exposant de _X|  
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|Obtient la mantisse et l’exposant de _X|  
|[isFinite](concurrency-fast-math-namespace-functions.md#isfinite)|Détermine si l’argument a une valeur finie|  
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Détermine si l’argument est une infinité|  
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|Détermine si l’argument est une valeur NaN|  
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Calcule le nombre réel de la mantisse et exposant|  
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Calcule le nombre réel de la mantisse et exposant|  
|[log](concurrency-fast-math-namespace-functions.md#log)|Calcule le logarithme de base e de l’argument|  
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Calcule le logarithme en base&10; de l’argument|  
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Calcule le logarithme en base&10; de l’argument|  
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Calcule le logarithme base&2; de l’argument|  
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Calcule le logarithme base&2; de l’argument|  
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Calcule le logarithme de base e de l’argument|  
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Fractionne _X en une fraction et un nombre entier.|  
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Fractionne _X en une fraction et un nombre entier.|  
|[pow](concurrency-fast-math-namespace-functions.md#pow)|Calcule _X élevé à la puissance de _Y|  
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Calcule _X élevé à la puissance de _Y|  
|[round](concurrency-fast-math-namespace-functions.md#round)|Arrondit _X à l’entier le plus proche|  
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|Arrondit _X à l’entier le plus proche|  
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Retourne l’inverse de la racine carrée de l’argument|  
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Retourne l’inverse de la racine carrée de l’argument|  
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Retourne le signe de l’argument|  
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Retourne le signe de l’argument|  
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Calcule la valeur du sinus de l’argument|  
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|Calcule le sinus et le cosinus valeur _X|  
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|Calcule le sinus et le cosinus valeur _X|  
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Calcule la valeur du sinus de l’argument|  
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|Calcule la valeur du sinus hyperbolique de l’argument|  
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Calcule la valeur du sinus hyperbolique de l’argument|  
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|Calcule la racine carrée de l’argument|  
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Calcule la racine carrée de l’argument|  
|[tan](concurrency-fast-math-namespace-functions.md#tan)|Calcule la valeur de l’argument de tangente|  
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Calcule la valeur de l’argument de tangente|  
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|Calcule la valeur de la tangente hyperbolique de l’argument|  
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Calcule la valeur de la tangente hyperbolique de l’argument|  
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Tronque l’argument pour le composant entier|  
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Tronque l’argument pour le composant entier|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_math.h  
  
 **Namespace :** Concurrency::fast_math  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency, espace de noms (C++ AMP)](concurrency-namespace-cpp-amp.md)

