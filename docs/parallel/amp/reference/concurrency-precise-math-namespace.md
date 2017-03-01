---
title: Concurrency::precise_math Namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::precise_math
dev_langs:
- C++
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b64bd3e3702701ae2685d6688d88988dd91dc5d0
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace"></a>Concurrency::precise_math, espace de noms
Les fonctions dans le `precise_math` espace de noms sont C99 conforme. À la fois simple précision et double précision versions de chaque fonction sont incluses. Par exemple, `acos` est la version double précision et `acosf` est la version simple précision. Ces fonctions, y compris les fonctions simple précision, requièrent la prise en charge de double précision étendue sur l’accélérateur. Vous pouvez utiliser la [Accelerator::supports_double_precision, données membres](accelerator-class.md#supports_double_precision) pour déterminer si vous pouvez exécuter ces fonctions sur un accélérateur spécifique. 

  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
namespace precise_math;  
```  
  
#### <a name="parameters"></a>Paramètres  
  
## <a name="members"></a>Membres  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[ACOS (fonction)](concurrency-precise-math-namespace-functions.md#acos)|Surchargé. Calcule l’arc cosinus de l’argument|  
|[acosf, fonction](concurrency-precise-math-namespace-functions.md#acosf)|Calcule l’arc cosinus de l’argument|  
|[ACOSH, fonction](concurrency-precise-math-namespace-functions.md#acosh)|Surchargé. Calcule le cosinus hyperbolique inverse de l’argument|  
|[acoshf, fonction](concurrency-precise-math-namespace-functions.md#acoshf)|Calcule le cosinus hyperbolique inverse de l’argument|  
|[ASIN (fonction)](concurrency-precise-math-namespace-functions.md#asin)|Surchargé. Calcule l’arc sinus de l’argument|  
|[asinf, fonction](concurrency-precise-math-namespace-functions.md#asinf)|Calcule l’arc sinus de l’argument|  
|[Asinh, fonction](concurrency-precise-math-namespace-functions.md#asinh)|Surchargé. Calcule le sinus hyperbolique inverse de l’argument|  
|[asinhf, fonction](concurrency-precise-math-namespace-functions.md#asinhf)|Calcule le sinus hyperbolique inverse de l’argument|  
|[ATAN (fonction)](concurrency-precise-math-namespace-functions.md#atan)|Surchargé. Calcule l’arc tangente de l’argument|  
|[ATAN2 (fonction)](concurrency-precise-math-namespace-functions.md#atan2)|Surchargé. Calcule l’arc tangente de _Y/_X|  
|[atan2f (fonction)](concurrency-precise-math-namespace-functions.md#atan2f)|Calcule l’arc tangente de _Y/_X|  
|[atanf, fonction](concurrency-precise-math-namespace-functions.md#atanf)|Calcule l’arc tangente de l’argument|  
|[ATANH, fonction](concurrency-precise-math-namespace-functions.md#atanh)|Surchargé. Calcule la tangente hyperbolique inverse de l’argument|  
|[atanhf, fonction](concurrency-precise-math-namespace-functions.md#atanhf)|Calcule la tangente hyperbolique inverse de l’argument|  
|[cbrt, fonction](concurrency-precise-math-namespace-functions.md#cbrt)|Surchargé. Calcule la racine cubique réelle de l’argument|  
|[cbrtf, fonction](concurrency-precise-math-namespace-functions.md#cbrtf)|Calcule la racine cubique réelle de l’argument|  
|[ceil (fonction)](concurrency-precise-math-namespace-functions.md#ceil)|Surchargé. Calcule le plafond de l’argument|  
|[ceilf, fonction](concurrency-precise-math-namespace-functions.md#ceilf)|Calcule le plafond de l’argument|  
|[copysign, fonction](concurrency-precise-math-namespace-functions.md#copysign)|Surchargé. Produit une valeur avec l’ampleur des _X et le signe de _Y|  
|[copysignf, fonction](concurrency-precise-math-namespace-functions.md#copysignf)|Produit une valeur avec l’ampleur des _X et le signe de _Y|  
|[COS (fonction)](concurrency-precise-math-namespace-functions.md#cos)|Surchargé. Calcule le cosinus de l’argument|  
|[cosf, fonction](concurrency-precise-math-namespace-functions.md#cosf)|Calcule le cosinus de l’argument|  
|[COSH (fonction)](concurrency-precise-math-namespace-functions.md#cosh)|Surchargé. Calcule la valeur de cosinus hyperbolique de l’argument|  
|[coshf, fonction](concurrency-precise-math-namespace-functions.md#coshf)|Calcule la valeur de cosinus hyperbolique de l’argument|  
|[cospi, fonction](concurrency-precise-math-namespace-functions.md#cospi)|Surchargé. Calcule la valeur du cosinus de pi * _X|  
|[cospif, fonction](concurrency-precise-math-namespace-functions.md#cospif)|Calcule la valeur du cosinus de pi * _X|  
|[ERF, fonction](concurrency-precise-math-namespace-functions.md#erf)|Surchargé. Calcule la fonction d’erreur de _X|  
|[ERFC, fonction](concurrency-precise-math-namespace-functions.md#erfc)|Surchargé. Calcule la fonction d’erreur complémentaire de _X|  
|[erfcf, fonction](concurrency-precise-math-namespace-functions.md#erfcf)|Calcule la fonction d’erreur complémentaire de _X|  
|[erfcinv, fonction](concurrency-precise-math-namespace-functions.md#erfcinv)|Surchargé. Calcule la fonction d’erreur complémentaire inverse de _X|  
|[erfcinvf, fonction](concurrency-precise-math-namespace-functions.md#erfcinvf)|Calcule la fonction d’erreur complémentaire inverse de _X|  
|[erff, fonction](concurrency-precise-math-namespace-functions.md#erff)|Calcule la fonction d’erreur de _X|  
|[erfinv, fonction](concurrency-precise-math-namespace-functions.md#erfinv)|Surchargé. Calcule la fonction d’erreur inverse de _X|  
|[erfinvf, fonction](concurrency-precise-math-namespace-functions.md#erfinvf)|Calcule la fonction d’erreur inverse de _X|  
|[EXP (fonction)](concurrency-precise-math-namespace-functions.md#exp)|Surchargé. Calcule la valeur exponentielle de l’argument de base e|  
|[exp10 (fonction)](concurrency-precise-math-namespace-functions.md#exp10)|Surchargé. Calcule la valeur exponentielle de l’argument de base&10;|  
|[exp10f (fonction)](concurrency-precise-math-namespace-functions.md#exp10f)|Calcule la valeur exponentielle de l’argument de base&10;|  
|[exp2 (fonction)](concurrency-precise-math-namespace-functions.md#exp2)|Surchargé. Calcule la valeur exponentielle de l’argument base-2|  
|[exp2f (fonction)](concurrency-precise-math-namespace-functions.md#exp2f)|Calcule la valeur exponentielle de l’argument base-2|  
|[expf, fonction](concurrency-precise-math-namespace-functions.md#expf)|Calcule la valeur exponentielle de l’argument de base e|  
|[expm1 (fonction)](concurrency-precise-math-namespace-functions.md#expm1)|Surchargé. Calcule l’exponentielle de base e de l’argument, moins 1|  
|[expm1f (fonction)](concurrency-precise-math-namespace-functions.md#expm1f)|Calcule l’exponentielle de base e de l’argument, moins 1|  
|[fabs, fonction](concurrency-precise-math-namespace-functions.md#fabs)|Surchargé. Retourne la valeur absolue de l’argument|  
|[fabsf, fonction](concurrency-precise-math-namespace-functions.md#fabsf)|Retourne la valeur absolue de l’argument|  
|[fdim, fonction](concurrency-precise-math-namespace-functions.md#fdim)|Surchargé. Détermine la différence entre les arguments positive|  
|[fdimf, fonction](concurrency-precise-math-namespace-functions.md#fdimf)|Détermine la différence entre les arguments positive|  
|[Floor, fonction](concurrency-precise-math-namespace-functions.md#floor)|Surchargé. Calcule le plancher de l’argument|  
|[floorf, fonction](concurrency-precise-math-namespace-functions.md#floorf)|Calcule le plancher de l’argument|  
|[FMA (fonction)](concurrency-precise-math-namespace-functions.md#fma)|Surchargé. Calcul (_X * _Y) + _Z, arrondi comme une seule opération ternaire|  
|[fmaf, fonction](concurrency-precise-math-namespace-functions.md#fmaf)|Calcul (_X * _Y) + _Z, arrondi comme une seule opération ternaire|  
|[Fmax, fonction](concurrency-precise-math-namespace-functions.md#fmax)|Surchargé. Déterminer la valeur numérique maximale des arguments|  
|[fmaxf, fonction](concurrency-precise-math-namespace-functions.md#fmaxf)|Déterminer la valeur numérique maximale des arguments|  
|[fmin, fonction](concurrency-precise-math-namespace-functions.md#fmin)|Surchargé. Déterminer la valeur numérique minimale des arguments|  
|[fminf, fonction](concurrency-precise-math-namespace-functions.md#fminf)|Déterminer la valeur numérique minimale des arguments|  
|[fmod, fonction (C++ AMP)](concurrency-precise-math-namespace-functions.md#fmod)|Surchargé. Calcule le reste à virgule flottante de _X/_Y|  
|[fmodf, fonction](concurrency-precise-math-namespace-functions.md#fmodf)|Calcule le reste à virgule flottante de _X/_Y|  
|[fpclassify, fonction](concurrency-precise-math-namespace-functions.md#fpclassify)|Surchargé. Classe de la valeur d’argument comme une valeur NaN, infinie, normale subnormal, zéro|  
|[frexp, fonction](concurrency-precise-math-namespace-functions.md#frexp)|Surchargé. Obtient la mantisse et l’exposant de _X|  
|[frexpf, fonction](concurrency-precise-math-namespace-functions.md#frexpf)|Obtient la mantisse et l’exposant de _X|  
|[hypot, fonction](concurrency-precise-math-namespace-functions.md#hypot)|Surchargé. Calcule la racine carrée de la somme des carrés des _X et _Y|  
|[hypotf, fonction](concurrency-precise-math-namespace-functions.md#hypotf)|Calcule la racine carrée de la somme des carrés des _X et _Y|  
|[ilogb, fonction](concurrency-precise-math-namespace-functions.md#ilogb)|Surchargé. Extraire l’exposant de _X comme une valeur int signée|  
|[ilogbf, fonction](concurrency-precise-math-namespace-functions.md#ilogbf)|Extraire l’exposant de _X comme une valeur int signée|  
|[isFinite, fonction](concurrency-precise-math-namespace-functions.md#isfinite)|Surchargé. Détermine si l’argument a une valeur finie|  
|[isinf, fonction](concurrency-precise-math-namespace-functions.md#isinf)|Surchargé. Détermine si l’argument est une infinité|  
|[isNaN (fonction)](concurrency-precise-math-namespace-functions.md#isnan)|Surchargé. Détermine si l’argument est une valeur NaN|  
|[isnormal, fonction](concurrency-precise-math-namespace-functions.md#isnormal)|Surchargé. Détermine si l’argument est normale|  
|[ldexp, fonction](concurrency-precise-math-namespace-functions.md#ldexp)|Surchargé. Calcule le nombre réel de la mantisse et exposant|  
|[ldexpf, fonction](concurrency-precise-math-namespace-functions.md#ldexpf)|Calcule le nombre réel de la mantisse et exposant|  
|[lgamma, fonction](concurrency-precise-math-namespace-functions.md#lgamma)|Surchargé. Calcule le logarithme népérien de la valeur absolue de gamma de l’argument|  
|[lgammaf, fonction](concurrency-precise-math-namespace-functions.md#lgammaf)|Calcule le logarithme népérien de la valeur absolue de gamma de l’argument|  
|[log, fonction](concurrency-precise-math-namespace-functions.md#log)|Surchargé. Calcule le logarithme de base e de l’argument|  
|[LOG10 (fonction)](concurrency-precise-math-namespace-functions.md#log10)|Surchargé. Calcule le logarithme en base&10; de l’argument|  
|[log10f (fonction)](concurrency-precise-math-namespace-functions.md#log10f)|Calcule le logarithme en base&10; de l’argument|  
|[log1p (fonction)](concurrency-precise-math-namespace-functions.md#log1p)|Surchargé. Calcule le logarithme de base e de 1 et de l’argument|  
|[log1pf (fonction)](concurrency-precise-math-namespace-functions.md#log1pf)|Calcule le logarithme de base e de 1 et de l’argument|  
|[LOG2 (fonction)](concurrency-precise-math-namespace-functions.md#log2)|Surchargé. Calcule le logarithme base&2; de l’argument|  
|[log2f (fonction)](concurrency-precise-math-namespace-functions.md#log2f)|Calcule le logarithme base&2; de l’argument|  
|[logb, fonction](concurrency-precise-math-namespace-functions.md#logb)|Surchargé. Extrait l’exposant de _X, comme une valeur d’entier signé dans un format à virgule flottante|  
|[logbf, fonction](concurrency-precise-math-namespace-functions.md#logbf)|Extrait l’exposant de _X, comme une valeur d’entier signé dans un format à virgule flottante|  
|[logf, fonction](concurrency-precise-math-namespace-functions.md#logf)|Calcule le logarithme de base e de l’argument|  
|[modf, fonction](concurrency-precise-math-namespace-functions.md#modf)|Surchargé. Fractionne _X en une fraction et un nombre entier.|  
|[modff, fonction](concurrency-precise-math-namespace-functions.md#modff)|Fractionne _X en une fraction et un nombre entier.|  
|[NaN (fonction)](concurrency-precise-math-namespace-functions.md#nan)|Retourne une valeur NaN silencieuse|  
|[nanf (fonction)](concurrency-precise-math-namespace-functions.md#nanf)|Retourne une valeur NaN silencieuse|  
|[nearbyint, fonction](concurrency-precise-math-namespace-functions.md#nearbyint)|Surchargé. Arrondit l’argument en une valeur entière dans un format à virgule flottante, à l’aide de la direction d’arrondi actuelle.|  
|[nearbyintf, fonction](concurrency-precise-math-namespace-functions.md#nearbyintf)|Arrondit l’argument en une valeur entière dans un format à virgule flottante, à l’aide de la direction d’arrondi actuelle.|  
|[nextafter, fonction](concurrency-precise-math-namespace-functions.md#nextafter)|Surchargé. Déterminer la valeur représentable, dans le type de la fonction, après _X dans la direction de _Y|  
|[nextafterf, fonction](concurrency-precise-math-namespace-functions.md#nextafterf)|Déterminer la valeur représentable, dans le type de la fonction, après _X dans la direction de _Y|  
|[phi, fonction](concurrency-precise-math-namespace-functions.md#phi)|Surchargé. Retourne la fonction de distribution cumulative de l’argument|  
|[phif, fonction](concurrency-precise-math-namespace-functions.md#phif)|Retourne la fonction de distribution cumulative de l’argument|  
|[Fonction pow](concurrency-precise-math-namespace-functions.md#pow)|Surchargé. Calcule _X élevé à la puissance de _Y|  
|[powf, fonction](concurrency-precise-math-namespace-functions.md#powf)|Calcule _X élevé à la puissance de _Y|  
|[probit, fonction](concurrency-precise-math-namespace-functions.md#probit)|Surchargé. Retourne la fonction de distribution cumulée inverse de l’argument|  
|[probitf, fonction](concurrency-precise-math-namespace-functions.md#probitf)|Retourne la fonction de distribution cumulée inverse de l’argument|  
|[rcbrt, fonction](concurrency-precise-math-namespace-functions.md#rcbrt)|Surchargé. Retourne l’inverse de la racine cubique de l’argument|  
|[rcbrtf, fonction](concurrency-precise-math-namespace-functions.md#rcbrtf)|Retourne l’inverse de la racine cubique de l’argument|  
|[Remainder (fonction)](concurrency-precise-math-namespace-functions.md#remainder)|Surchargé. Calcule le reste : _X REM _Y|  
|[remainderf, fonction](concurrency-precise-math-namespace-functions.md#remainderf)|Calcule le reste : _X REM _Y|  
|[remquo, fonction](concurrency-precise-math-namespace-functions.md#remquo)|Surchargé. Calcule le reste même comme _X REM _Y. Également calcule les 23 bits de poids faible de l’intégrale quotient _X/_Y, ainsi que cette valeur de la même signature que _X/_Y. Elle stocke cette valeur signée dans l’entier indiqué par _Quo.|  
|[remquof, fonction](concurrency-precise-math-namespace-functions.md#remquof)|Calcule le reste même comme _X REM _Y. Également calcule les 23 bits de poids faible de l’intégrale quotient _X/_Y, ainsi que cette valeur de la même signature que _X/_Y. Elle stocke cette valeur signée dans l’entier indiqué par _Quo.|  
|[Round (fonction)](concurrency-precise-math-namespace-functions.md#round)|Surchargé. Arrondit _X à l’entier le plus proche|  
|[roundf, fonction](concurrency-precise-math-namespace-functions.md#roundf)|Arrondit _X à l’entier le plus proche|  
|[rsqrt, fonction](concurrency-precise-math-namespace-functions.md#rsqrt)|Surchargé. Retourne l’inverse de la racine carrée de l’argument|  
|[rsqrtf, fonction](concurrency-precise-math-namespace-functions.md#rsqrtf)|Retourne l’inverse de la racine carrée de l’argument|  
|[scalb, fonction](concurrency-precise-math-namespace-functions.md#scalb)|Surchargé. Multiplie _X par FLT_RADIX à la _Y de l’alimentation|  
|[scalbf, fonction](concurrency-precise-math-namespace-functions.md#scalbf)|Multiplie _X par FLT_RADIX à la _Y de l’alimentation|  
|[scalbn, fonction](concurrency-precise-math-namespace-functions.md#scalbn)|Surchargé. Multiplie _X par FLT_RADIX à la _Y de l’alimentation|  
|[scalbnf, fonction](concurrency-precise-math-namespace-functions.md#scalbnf)|Multiplie _X par FLT_RADIX à la _Y de l’alimentation|  
|[signbit, fonction](concurrency-precise-math-namespace-functions.md#signbit)|Surchargé. Détermine si le signe de _X est négatif|  
|[signbitf, fonction](concurrency-precise-math-namespace-functions.md#signbitf)|Détermine si le signe de _X est négatif|  
|[SIN (fonction)](concurrency-precise-math-namespace-functions.md#sin)|Surchargé. Calcule la valeur du sinus de l’argument|  
|[sincos, fonction](concurrency-precise-math-namespace-functions.md#sincos)|Surchargé. Calcule le sinus et le cosinus valeur _X|  
|[sincosf, fonction](concurrency-precise-math-namespace-functions.md#sincosf)|Calcule le sinus et le cosinus valeur _X|  
|[Sinf, fonction](concurrency-precise-math-namespace-functions.md#sinf)|Calcule la valeur du sinus de l’argument|  
|[sinh (fonction)](concurrency-precise-math-namespace-functions.md#sinh)|Surchargé. Calcule la valeur du sinus hyperbolique de l’argument|  
|[sinhf, fonction](concurrency-precise-math-namespace-functions.md#sinhf)|Calcule la valeur du sinus hyperbolique de l’argument|  
|[sinpi, fonction](concurrency-precise-math-namespace-functions.md#sinpi)|Surchargé. Calcule la valeur du sinus de pi * _X|  
|[sinpif, fonction](concurrency-precise-math-namespace-functions.md#sinpif)|Calcule la valeur du sinus de pi * _X|  
|[SQRT (fonction)](concurrency-precise-math-namespace-functions.md#sqrt)|Surchargé. Calcule la racine squre de l’argument|  
|[sqrtf, fonction](concurrency-precise-math-namespace-functions.md#sqrtf)|Calcule la racine squre de l’argument|  
|[tan (fonction)](concurrency-precise-math-namespace-functions.md#tan)|Surchargé. Calcule la valeur de l’argument de tangente|  
|[tanf, fonction](concurrency-precise-math-namespace-functions.md#tanf)|Calcule la valeur de l’argument de tangente|  
|[TANH, fonction](concurrency-precise-math-namespace-functions.md#tanh)|Surchargé. Calcule la valeur de la tangente hyperbolique de l’argument|  
|[tanhf, fonction](concurrency-precise-math-namespace-functions.md#tanhf)|Calcule la valeur de la tangente hyperbolique de l’argument|  
|[tanpi, fonction](concurrency-precise-math-namespace-functions.md#tanpi)|Surchargé. Calcule la valeur de tangente de pi * _X|  
|[tanpif, fonction](concurrency-precise-math-namespace-functions.md#tanpif)|Calcule la valeur de tangente de pi * _X|  
|[tgamma, fonction](concurrency-precise-math-namespace-functions.md#tgamma)|Surchargé. Calcule la fonction gamma de _X|  
|[tgammaf, fonction](concurrency-precise-math-namespace-functions.md#tgammaf)|Calcule la fonction gamma de _X|  
|[trunc, fonction](concurrency-precise-math-namespace-functions.md#trunc)|Surchargé. Tronque l’argument pour le composant entier|  
|[truncf, fonction](concurrency-precise-math-namespace-functions.md#truncf)|Tronque l’argument pour le composant entier|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_math.h  
  
 **Espace de noms :** Concurrency  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

