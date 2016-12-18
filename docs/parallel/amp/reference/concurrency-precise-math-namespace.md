---
title: "Concurrency::precise_math, espace de noms | Microsoft Docs"
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
  - "amp_math/Concurrency::precise_math"
dev_langs: 
  - "C++"
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::precise_math, espace de noms
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Les fonctions dans l'espace de noms `precise_math` sont conforme C99 .  La simple précision et les versions à double précision de chaque fonction sont incluses.  Par exemple, `acos` est la version en double précision et `acosf` est la version en simple précision.  Ces fonctions, y compris les fonctions en simple précision, requièrent la prise en charge en double précision étendu sur l'accélérateur.  Vous pouvez utiliser [accelerator::supports\_double\_precision, données membres](../Topic/accelerator::supports_double_precision%20Data%20Member.md) pour déterminer si vous pouvez exécuter ces fonctions sur un accélérateur spécifique.  
  
## Syntaxe  
  
```vb  
namespace precise_math;  
```  
  
#### Paramètres  
  
## Membres  
  
### Fonctions  
  
|Name|Description|  
|----------|-----------------|  
|[Fonction acos](../Topic/acos%20Function.md)|Surchargé.  Calcule l'arccosinus de l'argument|  
|[acosf, fonction](../Topic/acosf%20Function.md)|Calcule l'arccosinus de l'argument|  
|[acosh, fonction](../Topic/acosh%20Function.md)|Surchargé.  Calcule le cosinus hyperbolique de l'argument|  
|[acoshf, fonction](../Topic/acoshf%20Function.md)|Calcule le cosinus hyperbolique de l'argument|  
|[Fonction asin](../Topic/asin%20Function.md)|Surchargé.  Calcule l'arcsinus de l'argument|  
|[asinf, fonction](../Topic/asinf%20Function.md)|Calcule l'arcsinus de l'argument|  
|[asinh, fonction](../Topic/asinh%20Function.md)|Surchargé.  Calcule le sinus hyperbolique inverse de l'argument|  
|[asinhf, fonction](../Topic/asinhf%20Function.md)|Calcule le sinus hyperbolique inverse de l'argument|  
|[Fonction atan](../Topic/atan%20Function.md)|Surchargé.  Calcule l'arctangente de l'argument|  
|[Fonction atan2](../Topic/atan2%20Function.md)|Surchargé.  Calcule l'arctangente de \_Y\/\_X|  
|[atan2f, fonction](../Topic/atan2f%20Function.md)|Calcule l'arctangente de \_Y\/\_X|  
|[atanf, fonction](../Topic/atanf%20Function.md)|Calcule l'arctangente de l'argument|  
|[atanh, fonction](../Topic/atanh%20Function.md)|Surchargé.  Calcule la tangente hyperbolique inverse de l'argument|  
|[atanhf, fonction](../Topic/atanhf%20Function.md)|Calcule la tangente hyperbolique inverse de l'argument|  
|[cbrt, fonction](../Topic/cbrt%20Function.md)|Surchargé.  Calcule la racine cubique réelle de l'argument|  
|[cbrtf, fonction](../Topic/cbrtf%20Function.md)|Calcule la racine cubique réelle de l'argument|  
|[Fonction ceil](../Topic/ceil%20Function.md)|Surchargé.  Calcule la valeur entière supérieure de l'argument|  
|[ceilf, fonction](../Topic/ceilf%20Function.md)|Calcule la valeur entière supérieure de l'argument|  
|[copysign, fonction](../Topic/copysign%20Function.md)|Surchargé.  Génère une valeur avec l'importance de \_X et le signe de \_Y|  
|[copysignf, fonction](../Topic/copysignf%20Function.md)|Génère une valeur avec l'importance de \_X et le signe de \_Y|  
|[Fonction cos](../Topic/cos%20Function.md)|Surchargé.  Calcule le cosinus de l'argument|  
|[cosf, fonction](../Topic/cosf%20Function.md)|Calcule le cosinus de l'argument|  
|[cosh, fonction](../Topic/cosh%20Function.md)|Surchargé.  Calcule la valeur du cosinus hyperbolique de l'argument|  
|[coshf, fonction](../Topic/coshf%20Function.md)|Calcule la valeur du cosinus hyperbolique de l'argument|  
|[cospi, fonction](../Topic/cospi%20Function.md)|Surchargé.  Calcule la valeur du cosinus de pi \* \_X|  
|[cospif, fonction](../Topic/cospif%20Function.md)|Calcule la valeur du cosinus de pi \* \_X|  
|[erf, fonction](../Topic/erf%20Function.md)|Surchargé.  Calcule la fonction d'erreur de \_X|  
|[erfc, fonction](../Topic/erfc%20Function.md)|Surchargé.  Calcule la fonction d'erreur complémentaire de \_X|  
|[erfcf, fonction](../Topic/erfcf%20Function.md)|Calcule la fonction d'erreur complémentaire de \_X|  
|[erfcinv, fonction](../Topic/erfcinv%20Function.md)|Surchargé.  Calcule la fonction erreur du complément inverse à \_X|  
|[erfcinvf, fonction](../Topic/erfcinvf%20Function.md)|Calcule la fonction erreur du complément inverse à \_X|  
|[erff, fonction](../Topic/erff%20Function.md)|Calcule la fonction d'erreur de \_X|  
|[erfinv, fonction](../Topic/erfinv%20Function.md)|Surchargé.  Calcule l'inverse de la fonction d'erreur de \_X|  
|[erfinvf, fonction](../Topic/erfinvf%20Function.md)|Calcule l'inverse de la fonction d'erreur de \_X|  
|[Fonction exp](../Topic/exp%20Function.md)|Surchargé.  Calcule la base e exponentielle du paramètre|  
|[exp10, fonction](../Topic/exp10%20Function.md)|Surchargé.  Calcule l´exponentiel en base\-10 de l'argument|  
|[exp10f, fonction](../Topic/exp10f%20Function.md)|Calcule l´exponentiel en base\-10 de l'argument|  
|[exp2, fonction](../Topic/exp2%20Function.md)|Surchargé.  Calcule l´exponentiel en base\-2 de l'argument|  
|[exp2f, fonction](../Topic/exp2f%20Function.md)|Calcule l´exponentiel en base\-2 de l'argument|  
|[expf, fonction](../Topic/expf%20Function.md)|Calcule la base e exponentielle du paramètre|  
|[expm1, fonction](../Topic/expm1%20Function.md)|Surchargé.  Calcule la base e exponentielle de l'argument, moins 1|  
|[expm1f, fonction](../Topic/expm1f%20Function.md)|Calcule la base e exponentielle de l'argument, moins 1|  
|[fabs, fonction](../Topic/fabs%20Function.md)|Surchargé.  Retourne la valeur absolue de l'argument|  
|[fabsf, fonction](../Topic/fabsf%20Function.md)|Retourne la valeur absolue de l'argument|  
|[fdim, fonction](../Topic/fdim%20Function.md)|Surchargé.  Détermine la différence positive entre les arguments|  
|[fdimf, fonction](../Topic/fdimf%20Function.md)|Détermine la différence positive entre les arguments|  
|[Fonction floor](../Topic/floor%20Function.md)|Surchargé.  Calcule le plus grand entier qui n'est pas supérieur à l'argument.|  
|[floorf, fonction](../Topic/floorf%20Function.md)|Calcule le plus grand entier qui n'est pas supérieur à l'argument.|  
|[fma, fonction](../Topic/fma%20Function.md)|Surchargé.  Calcule \(\_X \* \_Y\) \+ \_Z, arrondi en tant qu'opération ternaire|  
|[fmaf, fonction](../Topic/fmaf%20Function.md)|Calcule \(\_X \* \_Y\) \+ \_Z, arrondi en tant qu'opération ternaire|  
|[fmax, fonction](../Topic/fmax%20Function.md)|Surchargé.  Détermine la valeur numérique maximale des arguments|  
|[fmaxf, fonction](../Topic/fmaxf%20Function.md)|Détermine la valeur numérique maximale des arguments|  
|[fmin, fonction](../Topic/fmin%20Function.md)|Surchargé.  Détermine la valeur numérique minimale des arguments|  
|[fminf, fonction](../Topic/fminf%20Function.md)|Détermine la valeur numérique minimale des arguments|  
|[fmod, fonction \(C\+\+ AMP\)](../Topic/fmod%20Function%20\(C++%20AMP\).md)|Surchargé.  Calcule le reste à virgule flottante de \_X\/\_Y.|  
|[fmodf, fonction](../Topic/fmodf%20Function.md)|Calcule le reste à virgule flottante de \_X\/\_Y.|  
|[fpclassify, fonction](../Topic/fpclassify%20Function.md)|Surchargé.  Classifie la valeur de l'argument en tant que valeur non numérique \(NaN\) Non, infinie, normale, subnormal, zéro|  
|[frexp, fonction](../Topic/frexp%20Function.md)|Surchargé.  Obtient la mantisse et l'exposant de \_X|  
|[frexpf, fonction](../Topic/frexpf%20Function.md)|Obtient la mantisse et l'exposant de \_X|  
|[hypot, fonction](../Topic/hypot%20Function.md)|Surchargé.  Calcule la racine carrée de la somme des carrés de \_X et \_Y|  
|[hypotf, fonction](../Topic/hypotf%20Function.md)|Calcule la racine carrée de la somme des carrés de \_X et \_Y|  
|[ilogb, fonction](../Topic/ilogb%20Function.md)|Surchargé.  Récupère l'exposant de \_X sous forme d'int signé|  
|[ilogbf, fonction](../Topic/ilogbf%20Function.md)|Récupère l'exposant de \_X sous forme d'int signé|  
|[isfinite, fonction](../Topic/isfinite%20Function.md)|Surchargé.  Détermine si l'argument a une valeur finie|  
|[isinf, fonction](../Topic/isinf%20Function.md)|Surchargé.  Détermine si l'argument est un infini|  
|[isnan, fonction](../Topic/isnan%20Function.md)|Surchargé.  Détermine si l'argument est un NaN|  
|[isnormal, fonction](../Topic/isnormal%20Function.md)|Surchargé.  Détermine si l'argument est une normale|  
|[ldexp, fonction](../Topic/ldexp%20Function.md)|Surchargé.  Calcule un nombre réel à partir de la mantisse et de l'exposant.|  
|[ldexpf, fonction](../Topic/ldexpf%20Function.md)|Calcule un nombre réel à partir de la mantisse et de l'exposant.|  
|[lgamma, fonction](../Topic/lgamma%20Function.md)|Surchargé.  Calcule le logarithme népérien de la valeur absolue gamma de l'argument|  
|[lgammaf, fonction](../Topic/lgammaf%20Function.md)|Calcule le logarithme népérien de la valeur absolue gamma de l'argument|  
|[Fonction log](../Topic/log%20Function.md)|Surchargé.  Calcule le logarithme en base e de l'argument|  
|[log10, fonction](../Topic/log10%20Function.md)|Surchargé.  Calcule le logarithme en base 10 de l'argument.|  
|[log10f, fonction](../Topic/log10f%20Function.md)|Calcule le logarithme en base 10 de l'argument.|  
|[log1p, fonction](../Topic/log1p%20Function.md)|Surchargé.  Calcule le logarithme de base e de 1 ainsi que l'argument|  
|[log1pf, fonction](../Topic/log1pf%20Function.md)|Calcule le logarithme de base e de 1 ainsi que l'argument|  
|[log2, fonction](../Topic/log2%20Function.md)|Surchargé.  Calcule le logarithme de base 2 de l'argument|  
|[log2f, fonction](../Topic/log2f%20Function.md)|Calcule le logarithme de base 2 de l'argument|  
|[logb, fonction](../Topic/logb%20Function.md)|Surchargé.  Récupère l'exposant de \_X, comme valeur d'entier signé au format à virgule flottante|  
|[logbf, fonction](../Topic/logbf%20Function.md)|Récupère l'exposant de \_X, comme valeur d'entier signé au format à virgule flottante|  
|[logf, fonction](../Topic/logf%20Function.md)|Calcule le logarithme en base e de l'argument|  
|[modf, fonction](../Topic/modf%20Function.md)|Surchargé.  Fractionne \_X en une partie fractionnaire et une partie entière.|  
|[modff, fonction](../Topic/modff%20Function.md)|Fractionne \_X en une partie fractionnaire et une partie entière.|  
|[nan, fonction](../Topic/nan%20Function.md)|Retourne silencieusement NaN|  
|[nanf, fonction](../Topic/nanf%20Function.md)|Retourne silencieusement NaN|  
|[nearbyint, fonction](../Topic/nearbyint%20Function.md)|Surchargé.  Arrondit l'argument en une valeur entière à virgule flottante, à l'aide de la direction actuelle d'arrondi.|  
|[nearbyintf, fonction](../Topic/nearbyintf%20Function.md)|Arrondit l'argument en une valeur entière à virgule flottante, à l'aide de la direction actuelle d'arrondi.|  
|[nextafter, fonction](../Topic/nextafter%20Function.md)|Surchargé.  Déterminez la prochaine valeur représentable, dans le type de la fonction, après \_X dans la direction de \_Y|  
|[nextafterf, fonction](../Topic/nextafterf%20Function.md)|Déterminez la prochaine valeur représentable, dans le type de la fonction, après \_X dans la direction de \_Y|  
|[phi, fonction](../Topic/phi%20Function.md)|Surchargé.  Retourne la fonction de répartition cumulative de l'argument|  
|[phif, fonction](../Topic/phif%20Function.md)|Retourne la fonction de répartition cumulative de l'argument|  
|[Fonction pow](../Topic/pow%20Function.md)|Surchargé.  Calcule \_X élevé à la puissance de \_Y|  
|[powf, fonction](../Topic/powf%20Function.md)|Calcule \_X élevé à la puissance de \_Y|  
|[probit, fonction](../Topic/probit%20Function.md)|Surchargé.  Retourne la fonction de répartition cumulative inverse de l'argument|  
|[probitf, fonction](../Topic/probitf%20Function.md)|Retourne la fonction de répartition cumulative inverse de l'argument|  
|[rcbrt, fonction](../Topic/rcbrt%20Function.md)|Surchargé.  Retourne le réciproque de la racine cubique de l'argument|  
|[rcbrtf, fonction](../Topic/rcbrtf%20Function.md)|Retourne le réciproque de la racine cubique de l'argument|  
|[remainder, fonction](../Topic/remainder%20Function.md)|Surchargé.  Calcule le reste : \_X REM \_Y|  
|[remainderf, fonction](../Topic/remainderf%20Function.md)|Calcule le reste : \_X REM \_Y|  
|[remquo, fonction](../Topic/remquo%20Function.md)|Surchargé.  Calcule le même reste que \_X REM \_Y.  Calcule également les 23 bits inférieurs du quotient intégral \_X\/\_Y, et donne à cette valeur le même signe que \_X\/\_Y.  Il stocke cette valeur signée dans l'integer pointé par \_Quo.|  
|[remquof, fonction](../Topic/remquof%20Function.md)|Calcule le même reste que \_X REM \_Y.  Calcule également les 23 bits inférieurs du quotient intégral \_X\/\_Y, et donne à cette valeur le même signe que \_X\/\_Y.  Il stocke cette valeur signée dans l'integer pointé par \_Quo.|  
|[Fonction round](../Topic/round%20Function.md)|Surchargé.  Arrondit \_X à l'entier le plus proche|  
|[roundf, fonction](../Topic/roundf%20Function.md)|Arrondit \_X à l'entier le plus proche|  
|[rsqrt, fonction](../Topic/rsqrt%20Function.md)|Surchargé.  Retourne la réciproque de la racine carrée de l'argument|  
|[rsqrtf, fonction](../Topic/rsqrtf%20Function.md)|Retourne la réciproque de la racine carrée de l'argument|  
|[scalb, fonction](../Topic/scalb%20Function.md)|Surchargé.  Multiplie \_X par FLT\_RADIX puissance \_Y|  
|[scalbf, fonction](../Topic/scalbf%20Function.md)|Multiplie \_X par FLT\_RADIX puissance \_Y|  
|[scalbn, fonction](../Topic/scalbn%20Function.md)|Surchargé.  Multiplie \_X par FLT\_RADIX puissance \_Y|  
|[scalbnf, fonction](../Topic/scalbnf%20Function.md)|Multiplie \_X par FLT\_RADIX puissance \_Y|  
|[signbit, fonction](../Topic/signbit%20Function.md)|Surchargé.  Détermine si le signe de \_X est négatif|  
|[signbitf, fonction](../Topic/signbitf%20Function.md)|Détermine si le signe de \_X est négatif|  
|[Fonction sin](../Topic/sin%20Function.md)|Surchargé.  Calcule la valeur du sinus de l'argument|  
|[sincos, fonction](../Topic/sincos%20Function.md)|Surchargé.  Calcule la valeur du sinus et du cosinus du \_X|  
|[sincosf, fonction](../Topic/sincosf%20Function.md)|Calcule la valeur du sinus et du cosinus du \_X|  
|[sinf, fonction](../Topic/sinf%20Function.md)|Calcule la valeur du sinus de l'argument|  
|[sinh, fonction](../Topic/sinh%20Function.md)|Surchargé.  Calcule la valeur hyperbolique du sinus de l'argument|  
|[sinhf, fonction](../Topic/sinhf%20Function.md)|Calcule la valeur hyperbolique du sinus de l'argument|  
|[sinpi, fonction](../Topic/sinpi%20Function.md)|Surchargé.  Calcule la valeur du sinus de pi \* \_X|  
|[sinpif, fonction](../Topic/sinpif%20Function.md)|Calcule la valeur du sinus de pi \* \_X|  
|[Fonction sqrt](../Topic/sqrt%20Function.md)|Surchargé.  Calcule la racine carrée de l'argument|  
|[sqrtf, fonction](../Topic/sqrtf%20Function.md)|Calcule la racine carrée de l'argument|  
|[Fonction tan](../Topic/tan%20Function.md)|Surchargé.  Calcule la valeur de la tangente de l'argument|  
|[tanf, fonction](../Topic/tanf%20Function.md)|Calcule la valeur de la tangente de l'argument|  
|[tanh, fonction](../Topic/tanh%20Function.md)|Surchargé.  Calcule la valeur de la tangente hyperbolique de l'argument|  
|[tanhf, fonction](../Topic/tanhf%20Function.md)|Calcule la valeur de la tangente hyperbolique de l'argument|  
|[tanpi, fonction](../Topic/tanpi%20Function.md)|Surchargé.  Calcule la valeur de la tangente de pi \* \_X|  
|[tanpif, fonction](../Topic/tanpif%20Function.md)|Calcule la valeur de la tangente de pi \* \_X|  
|[tgamma, fonction](../Topic/tgamma%20Function.md)|Surchargé.  Calcule la fonction gamma de \_X|  
|[tgammaf, fonction](../Topic/tgammaf%20Function.md)|Calcule la fonction gamma de \_X|  
|[trunc, fonction](../Topic/trunc%20Function.md)|Surchargé.  Tronque l'argument en composant entier|  
|[truncf, fonction](../Topic/truncf%20Function.md)|Tronque l'argument en composant entier|  
  
## Configuration requise  
 **En\-tête:** amp\_math.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)