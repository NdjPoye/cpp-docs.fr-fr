---
title: Concurrency::fast_math Namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 293452bf0a01f7f83a8a41bcb511bc57c9d45f26
ms.lasthandoff: 02/24/2017

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
|[COS (fonction) (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|Calcule l’arc cosinus de l’argument|  
|[cosf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|Calcule l’arc cosinus de l’argument|  
|[ASIN, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#asin)|Calcule l’arc sinus de l’argument|  
|[asinf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#asinf)|Calcule l’arc sinus de l’argument|  
|[ATAN, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#atan)|Calcule l’arc tangente de l’argument|  
|[ATAN2, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#atan2)|Calcule l’arc tangente de _Y/_X|  
|[atan2f, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#atan2f)|Calcule l’arc tangente de _Y/_X|  
|[atanf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#atanf)|Calcule l’arc tangente de l’argument|  
|[ceil, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#ceil)|Calcule le plafond de l’argument|  
|[ceilf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#ceilf)|Calcule le plafond de l’argument|  
|[COS (fonction) (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|Calcule le cosinus de l’argument|  
|[cosf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|Calcule le cosinus de l’argument|  
|[COSH, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#cosh)|Calcule la valeur de cosinus hyperbolique de l’argument|  
|[coshf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#coshf)|Calcule la valeur de cosinus hyperbolique de l’argument|  
|[EXP, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#exp)|Calcule la valeur exponentielle de l’argument de base e|  
|[exp2, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#exp2)|Calcule la valeur exponentielle de l’argument base-2|  
|[exp2f, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#exp2f)|Calcule la valeur exponentielle de l’argument base-2|  
|[expf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#expf)|Calcule la valeur exponentielle de l’argument de base e|  
|[fabs, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fabs)|Retourne la valeur absolue de l’argument|  
|[fabsf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fabsf)|Retourne la valeur absolue de l’argument|  
|[Floor, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#floor)|Calcule le plancher de l’argument|  
|[floorf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#floorf)|Calcule le plancher de l’argument|  
|[Fmax, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fmax)|Déterminer la valeur numérique maximale des arguments|  
|[fmaxf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fmaxf)|Déterminer la valeur numérique maximale des arguments|  
|[fmin, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fmin)|Déterminer la valeur numérique minimale des arguments|  
|[fminf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fminf)|Déterminer la valeur numérique minimale des arguments|  
|[fmod, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fmod)|Calcule le reste à virgule flottante de _X/_Y|  
|[fmodf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#fmodf)|Calcule le reste à virgule flottante de _X/_Y|  
|[frexp, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#frexp)|Obtient la mantisse et l’exposant de _X|  
|[frexpf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#frexpf)|Obtient la mantisse et l’exposant de _X|  
|[isFinite, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#isfinite)|Détermine si l’argument a une valeur finie|  
|[isinf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#isinf)|Détermine si l’argument est une infinité|  
|[isNaN, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#isnan)|Détermine si l’argument est une valeur NaN|  
|[ldexp, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#ldexp)|Calcule le nombre réel de la mantisse et exposant|  
|[ldexpf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#ldexpf)|Calcule le nombre réel de la mantisse et exposant|  
|[log, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#log)|Calcule le logarithme de base e de l’argument|  
|[LOG10, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#log10)|Calcule le logarithme en base&10; de l’argument|  
|[log10f, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#log10f)|Calcule le logarithme en base&10; de l’argument|  
|[LOG2, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#log2)|Calcule le logarithme base&2; de l’argument|  
|[log2f, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#log2f)|Calcule le logarithme base&2; de l’argument|  
|[logf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#logf)|Calcule le logarithme de base e de l’argument|  
|[modf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#modf)|Fractionne _X en une fraction et un nombre entier.|  
|[modff, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#modff)|Fractionne _X en une fraction et un nombre entier.|  
|[pow (fonction) (fast_math)](concurrency-fast-math-namespace-functions.md#pow)|Calcule _X élevé à la puissance de _Y|  
|[powf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#powf)|Calcule _X élevé à la puissance de _Y|  
|[Round, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#round)|Arrondit _X à l’entier le plus proche|  
|[roundf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#roundf)|Arrondit _X à l’entier le plus proche|  
|[rsqrt, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrt)|Retourne l’inverse de la racine carrée de l’argument|  
|[rsqrtf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrtf)|Retourne l’inverse de la racine carrée de l’argument|  
|[signbit, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#signbit)|Retourne le signe de l’argument|  
|[signbitf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#signbitf)|Retourne le signe de l’argument|  
|[sin, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sin)|Calcule la valeur du sinus de l’argument|  
|[sincos, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sincos)|Calcule le sinus et le cosinus valeur _X|  
|[sincosf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sincosf)|Calcule le sinus et le cosinus valeur _X|  
|[Sinf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sinf)|Calcule la valeur du sinus de l’argument|  
|[SINH, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sinh)|Calcule la valeur du sinus hyperbolique de l’argument|  
|[sinhf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sinhf)|Calcule la valeur du sinus hyperbolique de l’argument|  
|[SQRT, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sqrt)|Calcule la racine carrée de l’argument|  
|[sqrtf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#sqrtf)|Calcule la racine carrée de l’argument|  
|[tan, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#tan)|Calcule la valeur de l’argument de tangente|  
|[tanf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#tanf)|Calcule la valeur de l’argument de tangente|  
|[TANH, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#tanh)|Calcule la valeur de la tangente hyperbolique de l’argument|  
|[tanhf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#tanhf)|Calcule la valeur de la tangente hyperbolique de l’argument|  
|[trunc, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#trunc)|Tronque l’argument pour le composant entier|  
|[truncf, fonction (fast_math)](concurrency-fast-math-namespace-functions.md#truncf)|Tronque l’argument pour le composant entier|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_math.h  
  
 **Namespace :** Concurrency::fast_math  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

