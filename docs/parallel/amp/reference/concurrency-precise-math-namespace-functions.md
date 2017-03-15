---
title: "Fonctions d’espace de noms Concurrency::precise_math | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 73273a58f73860c77810a6ab59def560962f9539
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace-functions"></a>Fonctions d’espace de noms Concurrency::precise_math
||||  
|-|-|-|  
|[ACOS (fonction)](#acos)|[acosf, fonction](#acosf)|[ACOSH, fonction](#acosh)|  
|[acoshf, fonction](#acoshf)|[ASIN (fonction)](#asin)|[asinf, fonction](#asinf)|  
|[Asinh, fonction](#asinh)|[asinhf, fonction](#asinhf)|[ATAN (fonction)](#atan)|  
|[ATAN2 (fonction)](#atan2)|[atan2f (fonction)](#atan2f)|[atanf, fonction](#atanf)|  
|[ATANH, fonction](#atanh)|[atanhf, fonction](#atanhf)|[cbrt, fonction](#cbrt)|  
|[cbrtf, fonction](#cbrtf)|[ceil (fonction)](#ceil)|[ceilf, fonction](#ceilf)|  
|[copysign, fonction](#copysign)|[copysignf, fonction](#copysignf)|[COS (fonction)](#cos)|  
|[cosf, fonction](#cosf)|[COSH (fonction)](#cosh)|[coshf, fonction](#coshf)|  
|[cospi, fonction](#cospi)|[cospif, fonction](#cospif)|[ERF, fonction](#erf)|  
|[ERFC, fonction](#erfc)|[erfcf, fonction](#erfcf)|[erfcinv, fonction](#erfcinv)|  
|[erfcinvf, fonction](#erfcinvf)|[erff, fonction](#erff)|[erfinv, fonction](#erfinv)|  
|[erfinvf, fonction](#erfinvf)|[EXP (fonction)](#exp)|[exp10 (fonction)](#exp10)|  
|[exp10f (fonction)](#exp10f)|[exp2 (fonction)](#exp2)|[exp2f (fonction)](#exp2f)|  
|[expf, fonction](#expf)|[expm1 (fonction)](#expm1)|[expm1f (fonction)](#expm1f)|  
|[fabs, fonction](#fabs)|[fabsf, fonction](#fabsf)|[Floor, fonction](#floor)| 
|[fdim, fonction](#fdim)|[fdimf, fonction](#fdimf)|| 
|[floorf, fonction](#floorf)|[FMA (fonction)](#fma)|[fmaf, fonction](#fmaf)|
[Fmax, fonction](#fmax)|[fmaxf, fonction](#fmaxf)|| 
|[fmin, fonction](#fmin)|[fminf, fonction](#fminf)|[fmod, fonction](#fmod)|  
|[fmodf, fonction](#fmodf)|[fpclassify, fonction](#fpclassify)|[frexp, fonction](#frexp)|  
|[frexpf, fonction](#frexpf)|[hypot, fonction](#hypot)|[hypotf, fonction](#hypotf)|  
|[ilogb, fonction](#ilogb)|[ilogbf, fonction](#ilogbf)|[isFinite, fonction](#isfinite)|  
|[isinf, fonction](#isinf)|[isNaN (fonction)](#isnan)|[isnormal, fonction](#isnormal)|  
|[ldexp, fonction](#ldexp)|[ldexpf, fonction](#ldexpf)|[lgamma, fonction](#lgamma)|  
|[lgammaf, fonction](#lgammaf)|[log, fonction](#log)|[LOG10 (fonction)](#log10)|  
|[log10f (fonction)](#log10f)|[log1p (fonction)](#log1p)|[log1pf (fonction)](#log1pf)|  
|[LOG2 (fonction)](#log2)|[log2f (fonction)](#log2f)|[logb, fonction](#logb)|  
|[logbf, fonction](#logbf)|[logf, fonction](#logf)|[modf, fonction](#modf)|  
|[modff, fonction](#modff)|[NaN (fonction)](#nan)|[nanf (fonction)](#nanf)|  
|[nearbyint, fonction](#nearbyint)|[nearbyintf, fonction](#nearbyintf)|[nextafter, fonction](#nextafter)|  
|[nextafterf, fonction](#nextafterf)|[phi, fonction](#phi)|[phif, fonction](#phif)|  
|[Fonction pow](#pow)|[powf, fonction](#powf)|[probit, fonction](#probit)|  
|[probitf, fonction](#probitf)|[rcbrt, fonction](#rcbrt)|[rcbrtf, fonction](#rcbrtf)|  
|[Remainder (fonction)](#remainder)|[remainderf, fonction](#remainderf)|[remquo, fonction](#remquo)|  
|[remquof, fonction](#remquof)|[Round (fonction)](#round)|[roundf, fonction](#roundf)|  
|[rsqrt, fonction](#rsqrt)|[rsqrtf, fonction](#rsqrtf)|[scalb, fonction](#scalb)|  
|[scalbf, fonction](#scalbf)|[scalbn, fonction](#scalbn)|[scalbnf, fonction](#scalbnf)|  
|[signbit, fonction](#signbit)|[signbitf, fonction](#signbitf)|[SIN (fonction)](#sin)|  
|[sincos, fonction](#sincos)|[sincosf, fonction](#sincosf)|[Sinf, fonction](#sinf)|  
|[sinh (fonction)](#sinh)|[sinhf, fonction](#sinhf)|[sinpi, fonction](#sinpi)|  
|[sinpif, fonction](#sinpif)|[SQRT (fonction)](#sqrt)|[sqrtf, fonction](#sqrtf)|  
|[tan (fonction)](#tan)|[tanf, fonction](#tanf)|[TANH, fonction](#tanh)|  
|[tanhf, fonction](#tanhf)|[tanpi, fonction](#tanpi)|[tanpif, fonction](#tanpif)|  
|[tgamma, fonction](#tgamma)|[tgammaf, fonction](#tgammaf)|[trunc, fonction](#trunc)|  
|[truncf, fonction](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>ACOS (fonction)  
 Calcule l’arc cosinus de l’argument  
  
```  
inline float acos(float _X) restrict(amp);

 
inline double acos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc cosinus de l’argument  
  
##  <a name="a-nameacosfa--acosf-function"></a><a name="acosf"></a>acosf, fonction  
 Calcule l’arc cosinus de l’argument  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc cosinus de l’argument  
  
##  <a name="a-nameacosha--acosh-function"></a><a name="acosh"></a>ACOSH, fonction  
 Calcule le cosinus hyperbolique inverse de l’argument  
  
```  
inline float acosh(float _X) restrict(amp);

 
inline double acosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc cosinus hyperbolique de l’argument  
  
##  <a name="a-nameacoshfa--acoshf-function"></a><a name="acoshf"></a>acoshf, fonction  
 Calcule le cosinus hyperbolique inverse de l’argument  
  
```  
inline float acoshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc cosinus hyperbolique de l’argument  
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>ASIN (fonction)  
 Calcule l’arc sinus de l’argument  
  
```  
inline float asin(float _X) restrict(amp);

 
inline double asin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’arc sinus de l’argument  
  
##  <a name="a-nameasinfa--asinf-function"></a><a name="asinf"></a>asinf, fonction  
 Calcule l’arc sinus de l’argument  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’arc sinus de l’argument  
  
##  <a name="a-nameasinha--asinh-function"></a><a name="asinh"></a>Asinh, fonction  
 Calcule le sinus hyperbolique inverse de l’argument  
  
```  
inline float asinh(float _X) restrict(amp);

 
inline double asinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus hyperbolique de l’argument  
  
##  <a name="a-nameasinhfa--asinhf-function"></a><a name="asinhf"></a>asinhf, fonction  
 Calcule le sinus hyperbolique inverse de l’argument  
  
```  
inline float asinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus hyperbolique de l’argument  
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>ATAN (fonction)  
 Calcule l’arc tangente de l’argument  
  
```  
inline float atan(float _X) restrict(amp);

 
inline double atan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc tangent de l’argument  
  
##  <a name="a-nameatan2a--atan2-function"></a><a name="atan2"></a>ATAN2 (fonction)  
 Calcule l’arc tangente de _Y/_X  
  
```  
inline float atan2(
    float _Y,  
    float _X) restrict(amp);

 
inline double atan2(
    double _Y,  
    double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Y`  
 Valeur à virgule flottante  
  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc tangent de _Y/_X  
  
##  <a name="a-nameatan2fa--atan2f-function"></a><a name="atan2f"></a>atan2f (fonction)  
 Calcule l’arc tangente de _Y/_X  
  
```  
inline float atan2f(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Y`  
 Valeur à virgule flottante  
  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc tangent de _Y/_X  
  
##  <a name="a-nameatanfa--atanf-function"></a><a name="atanf"></a>atanf, fonction  
 Calcule l’arc tangente de l’argument  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur d’arc tangent de l’argument  
  
##  <a name="a-nameatanha--atanh-function"></a><a name="atanh"></a>ATANH, fonction  
 Calcule la tangente hyperbolique inverse de l’argument  
  
```  
inline float atanh(float _X) restrict(amp);

 
inline double atanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de tangente hyperbolique inverse de l’argument  
  
##  <a name="a-nameatanhfa--atanhf-function"></a><a name="atanhf"></a>atanhf, fonction  
 Calcule la tangente hyperbolique inverse de l’argument  
  
```  
inline float atanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de tangente hyperbolique inverse de l’argument  
  
##  <a name="a-namecbrta--cbrt-function"></a><a name="cbrt"></a>cbrt, fonction  
 Calcule la racine cubique réelle de l’argument  
  
```  
inline float cbrt(float _X) restrict(amp);

 
inline double cbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la racine cubique réelle de l’argument  
  
##  <a name="a-namecbrtfa--cbrtf-function"></a><a name="cbrtf"></a>cbrtf, fonction  
 Calcule la racine cubique réelle de l’argument  
  
```  
inline float cbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la racine cubique réelle de l’argument  
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil (fonction)  
 Calcule le plafond de l’argument  
  
```  
inline float ceil(float _X) restrict(amp);

 
inline double ceil(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le plafond de l’argument  
  
##  <a name="a-nameceilfa--ceilf-function"></a><a name="ceilf"></a>ceilf, fonction  
 Calcule le plafond de l’argument  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le plafond de l’argument  
  
##  <a name="a-namecopysigna--copysign-function"></a><a name="copysign"></a>copysign, fonction  
 Produit une valeur avec l’ampleur des _X et le signe de _Y  
  
```  
inline float copysign(
    float _X,  
    float _Y) restrict(amp);

 
inline double copysign(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur avec l’ampleur des _X et le signe de _Y  
  
##  <a name="a-namecopysignfa--copysignf-function"></a><a name="copysignf"></a>copysignf, fonction  
 Produit une valeur avec l’ampleur des _X et le signe de _Y  
  
```  
inline float copysignf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur avec l’ampleur des _X et le signe de _Y  
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>COS (fonction)  
 Calcule le cosinus de l’argument  
  
```  
inline float cos(float _X) restrict(amp);

 
inline double cos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de cosinus de l’argument  
  
##  <a name="a-namecosfa--cosf-function"></a><a name="cosf"></a>cosf, fonction  
 Calcule le cosinus de l’argument  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de cosinus de l’argument  
  
##  <a name="a-namecosha--cosh-function"></a><a name="cosh"></a>COSH (fonction)  
 Calcule la valeur de cosinus hyperbolique de l’argument  
  
```  
inline float cosh(float _X) restrict(amp);

 
inline double cosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de cosinus hyperbolique de l’argument  
  
##  <a name="a-namecoshfa--coshf-function"></a><a name="coshf"></a>coshf, fonction  
 Calcule la valeur de cosinus hyperbolique de l’argument  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de cosinus hyperbolique de l’argument  
  
##  <a name="a-namecospia--cospi-function"></a><a name="cospi"></a>cospi, fonction  
 Calcule la valeur du cosinus de pi * _X  
  
```  
inline float cospi(float _X) restrict(amp);

 
inline double cospi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du cosinus de pi * _X  
  
##  <a name="a-namecospifa--cospif-function"></a><a name="cospif"></a>cospif, fonction  
 Calcule la valeur du cosinus de pi * _X  
  
```  
inline float cospif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du cosinus de pi * _X  
  
##  <a name="a-nameerfa--erf-function"></a><a name="erf"></a>ERF, fonction  
 Calcule la fonction d’erreur de _X  
  
```  
inline float erf(float _X) restrict(amp);

 
inline double erf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction d’erreur de _X  
  
##  <a name="a-nameerfca--erfc-function"></a><a name="erfc"></a>ERFC, fonction  
 Calcule la fonction d’erreur complémentaire de _X  
  
```  
inline float erfc(float _X) restrict(amp);

 
inline double erfc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction d’erreur complémentaire de _X  
  
##  <a name="a-nameerfcfa--erfcf-function"></a><a name="erfcf"></a>erfcf, fonction  
 Calcule la fonction d’erreur complémentaire de _X  
  
```  
inline float erfcf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction d’erreur complémentaire de _X  
  
##  <a name="a-nameerfcinva--erfcinv-function"></a><a name="erfcinv"></a>erfcinv, fonction  
 Calcule la fonction d’erreur complémentaire inverse de _X  
  
```  
inline float erfcinv(float _X) restrict(amp);

 
inline double erfcinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction d’erreur complémentaire inverse de _X  
  
##  <a name="a-nameerfcinvfa--erfcinvf-function"></a><a name="erfcinvf"></a>erfcinvf, fonction  
 Calcule la fonction d’erreur complémentaire inverse de _X  
  
```  
inline float erfcinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction d’erreur complémentaire inverse de _X  
  
##  <a name="a-nameerffa--erff-function"></a><a name="erff"></a>erff, fonction  
 Calcule la fonction d’erreur de _X  
  
```  
inline float erff(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction d’erreur de _X  
  
##  <a name="a-nameerfinva--erfinv-function"></a><a name="erfinv"></a>erfinv, fonction  
 Calcule la fonction d’erreur inverse de _X  
  
```  
inline float erfinv(float _X) restrict(amp);

 
inline double erfinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de l’erreur inverse de _X  
  
##  <a name="a-nameerfinvfa--erfinvf-function"></a><a name="erfinvf"></a>erfinvf, fonction  
 Calcule la fonction d’erreur inverse de _X  
  
```  
inline float erfinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de l’erreur inverse de _X  
  
##  <a name="a-nameexp10a--exp10-function"></a><a name="exp10"></a>exp10 (fonction)  
 Calcule la valeur exponentielle de l’argument de base&10;  
  
```  
inline float exp10(float _X) restrict(amp);

 
inline double exp10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur exponentielle de l’argument de base&10;  
  
##  <a name="a-nameexp10fa--exp10f-function"></a><a name="exp10f"></a>exp10f (fonction)  
 Calcule la valeur exponentielle de l’argument de base&10;  
  
```  
inline float exp10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur exponentielle de l’argument de base&10;  
  
##  <a name="a-nameexpm1a--expm1-function"></a><a name="expm1"></a>expm1 (fonction)  
 Calcule l’exponentielle de base e de l’argument, moins 1  
  
```  
inline float expm1(float exponent) restrict(amp);

 
inline double expm1(double exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `exponent`  
 Le terme exponentiel *n* de l’expression mathématique `e` <sup>n</sup>, où `e` est la base du logarithme népérien.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’exponentielle de base e de l’argument, moins 1  
  
##  <a name="a-nameexpm1fa--expm1f-function"></a><a name="expm1f"></a>expm1f (fonction)  
 Calcule l’exponentielle de base e de l’argument, moins 1  
  
```  
inline float expm1f(float exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `exponent`  
 Le terme exponentiel *n* de l’expression mathématique `e` <sup>n</sup>, où `e` est la base du logarithme népérien.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’exponentielle de base e de l’argument, moins 1  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>EXP (fonction)  
 Calcule la valeur exponentielle de l’argument de base e  
  
```  
inline float exp(float _X) restrict(amp);

 
inline double exp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur exponentielle de l’argument de base e  
  
##  <a name="a-nameexpfa--expf-function"></a><a name="expf"></a>expf, fonction  
 Calcule la valeur exponentielle de l’argument de base e  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur exponentielle de l’argument de base e  
  
##  <a name="a-nameexp2a--exp2-function"></a><a name="exp2"></a>exp2 (fonction)  
 Calcule la valeur exponentielle de l’argument base-2  
  
```  
inline float exp2(float _X) restrict(amp);

 
inline double exp2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur exponentielle de l’argument base-2  
  
##  <a name="a-nameexp2fa--exp2f-function"></a><a name="exp2f"></a>exp2f (fonction)  
 Calcule la valeur exponentielle de l’argument base-2  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur exponentielle de l’argument base-2  
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>fabs, fonction  
 Retourne la valeur absolue de l’argument  
  
```  
inline float fabs(float _X) restrict(amp);

 
inline double fabs(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur absolue de l’argument  
  
##  <a name="a-namefabsfa--fabsf-function"></a><a name="fabsf"></a>fabsf, fonction  
 Retourne la valeur absolue de l’argument  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur absolue de l’argument  

## <a name="a-namefdima-fdim-function"></a><a name="fdim"></a>fdim, fonction  
Calcule la différence entre les arguments positive.
```  
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
``` 
### <a name="parameters"></a>Paramètres
`_X`Valeur à virgule flottante `_Y` valeur à virgule flottante


### <a name="return-value"></a>Valeur de retour
La différence entre _X et _Y si _X est supérieure à _Y ; Sinon, +&0;.
 
## <a name="a-namefdimfa-fdimf-function"></a><a name="fdimf"></a>fdimf, fonction
Calcule la différence entre les arguments positive.
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```
### <a name="parameters"></a>Paramètres
`_X`Valeur à virgule flottante `_Y` valeur à virgule flottante

### <a name="return-value"></a>Valeur de retour
La différence entre _X et _Y si _X est supérieure à _Y ; Sinon, +&0;. 
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>Floor, fonction  
 Calcule le plancher de l’argument  
  
```  
inline float floor(float _X) restrict(amp);

 
inline double floor(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le plancher de l’argument  
  
##  <a name="a-namefloorfa--floorf-function"></a><a name="floorf"></a>floorf, fonction  
 Calcule le plancher de l’argument  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le plancher de l’argument  

## <a name="a-namefma-fma-function"></a><a name="fma">FMA (fonction)  
Calcule le produit des premier et deuxième arguments spécifiés, puis ajoute le troisième argument spécifié au résultat ; le calcul entière est effectué en une seule opération.
```
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```
### <a name="parameters"></a>Paramètres
`_X`Le premier argument à virgule flottante.
`_Y`Le deuxième argument à virgule flottante.
`_Z`Le troisième argument à virgule flottante.

### <a name="return-value"></a>Valeur de retour
Le résultat de l’expression (_X * _Y) + _Z. Le calcul entière est effectué en une seule opération ; Autrement dit, les sous-expressions sont calculées à une précision infinie et uniquement le résultat final est arrondi. 

## <a name="a-namefmafa-fmaf-function"></a><a name="fmaf"></a>fmaf, fonction  
Calcule le produit des premier et deuxième arguments spécifiés, puis ajoute le troisième argument spécifié au résultat ; le calcul entière est effectué en une seule opération.
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```  
### <a name="parameters"></a>Paramètres
`_X`Le premier argument à virgule flottante.
`_Y`Le deuxième argument à virgule flottante.
`_Z`Le troisième argument à virgule flottante.

### <a name="return-value"></a>Valeur de retour
Le résultat de l’expression (_X * _Y) + _Z. Le calcul entière est effectué en une seule opération ; Autrement dit, les sous-expressions sont calculées à une précision infinie et uniquement le résultat final est arrondi.
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>Fmax, fonction  
 Déterminer la valeur numérique maximale des arguments  
  
```  
inline float fmax(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmax(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique maximale des arguments  
  
##  <a name="a-namefmaxfa--fmaxf-function"></a><a name="fmaxf"></a>fmaxf, fonction  
 Déterminer la valeur numérique maximale des arguments  
  
```  
inline float fmaxf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique maximale des arguments  
  
##  <a name="a-namefmina--fmin-function"></a><a name="fmin"></a>fmin, fonction  
 Déterminer la valeur numérique minimale des arguments  
  
```  
inline float fmin(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmin(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique minimale des arguments  
  
##  <a name="a-namefminfa--fminf-function"></a><a name="fminf"></a>fminf, fonction  
 Déterminer la valeur numérique minimale des arguments  
  
```  
inline float fminf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner la valeur numérique minimale des arguments  
  
##  <a name="a-namefmoda--fmod-function-c-amp"></a><a name="fmod"></a>fmod, fonction (C++ AMP)  
 Calcule le reste du premier argument spécifié divisé par le deuxième argument spécifié.  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmod(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Le premier argument à virgule flottante.  
  
 `_Y`  
 Le deuxième argument à virgule flottante.  
  
### <a name="return-value"></a>Valeur de retour  
 Le reste de `_X` divisé par `_Y`; autrement dit, la valeur de `_X`  -  `_Y` *n*, où *n* est un entier tel que l’ampleur du `_X`  -  `_Y` *n* est inférieure à la grandeur de `_Y`.  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>fmodf, fonction  
 Calcule le reste du premier argument spécifié divisé par le deuxième argument spécifié.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Le premier argument à virgule flottante.  
  
 `_Y`  
 Le deuxième argument à virgule flottante.  
  
### <a name="return-value"></a>Valeur de retour  
 Le reste de `_X` divisé par `_Y`; autrement dit, la valeur de `_X`  -  `_Y` *n*, où *n* est un entier tel que l’ampleur du `_X`  -  `_Y` *n* est inférieure à la grandeur de `_Y`.  
  
##  <a name="a-namefpclassifya--fpclassify-function"></a><a name="fpclassify"></a>fpclassify, fonction  
 Classe de la valeur d’argument comme une valeur NaN, infinie, normale subnormal, zéro  
  
```  
inline int fpclassify(float _X) restrict(amp);

 
inline int fpclassify(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de la macro de classification nombre approprié à la valeur de l’argument.  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>frexp, fonction  
 Obtient la mantisse et l’exposant de _X  
  
```  
inline float frexp(
    float _X,  
    _Out_ int* _Exp) restrict(amp);

 
inline double frexp(
    double _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Exp`  
 Renvoie l’exposant entier de _X en valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie la mantisse _X  
  
##  <a name="a-namefrexpfa--frexpf-function"></a><a name="frexpf"></a>frexpf, fonction  
 Obtient la mantisse et l’exposant de _X  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Exp`  
 Renvoie l’exposant entier de _X en valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie la mantisse _X  
  
##  <a name="a-namehypota--hypot-function"></a><a name="hypot"></a>hypot, fonction  
 Calcule la racine carrée de la somme des carrés des _X et _Y  
  
```  
inline float hypot(
    float _X,  
    float _Y) restrict(amp);

 
inline double hypot(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la racine carrée de la somme des carrés des _X et _Y  
  
##  <a name="a-namehypotfa--hypotf-function"></a><a name="hypotf"></a>hypotf, fonction  
 Calcule la racine carrée de la somme des carrés des _X et _Y  
  
```  
inline float hypotf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la racine carrée de la somme des carrés des _X et _Y  
  
##  <a name="a-nameilogba--ilogb-function"></a><a name="ilogb"></a>ilogb, fonction  
 Extraire l’exposant de _X comme une valeur int signée  
  
```  
inline int ilogb(float _X) restrict(amp);

 
inline int ilogb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie l’exposant de _X comme une valeur int signée  
  
##  <a name="a-nameilogbfa--ilogbf-function"></a><a name="ilogbf"></a>ilogbf, fonction  
 Extraire l’exposant de _X comme une valeur int signée  
  
```  
inline int ilogbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie l’exposant de _X comme une valeur int signée  
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>isFinite, fonction  
 Détermine si l’argument a une valeur finie  
  
```  
inline int isfinite(float _X) restrict(amp);

 
inline int isfinite(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si l’argument a la valeur finie  
  
##  <a name="a-nameisinfa--isinf-function"></a><a name="isinf"></a>isinf, fonction  
 Détermine si l’argument est une infinité  
  
```  
inline int isinf(float _X) restrict(amp);

 
inline int isinf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si l’argument a une valeur infinie  
  
##  <a name="a-nameisnana--isnan-function"></a><a name="isnan"></a>isNaN (fonction)  
 Détermine si l’argument est une valeur NaN  
  
```  
inline int isnan(float _X) restrict(amp);

 
inline int isnan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si l’argument a une valeur NaN  
  
##  <a name="a-nameisnormala--isnormal-function"></a><a name="isnormal"></a>isnormal, fonction  
 Détermine si l’argument est normale  
  
```  
inline int isnormal(float _X) restrict(amp);

 
inline int isnormal(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si l’argument a la valeur normale  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>ldexp, fonction  
 Calcule le nombre réel de la mantisse spécifié et l’exposant.  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);

 
inline double ldexp(
    double _X,  
    double _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, la mantisse  
  
 `_Exp`  
 Valeur entière, exposant  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * 2 ^ _Exp  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>ldexpf, fonction  
 Calcule le nombre réel de la mantisse spécifié et l’exposant.  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, la mantisse  
  
 `_Exp`  
 Valeur entière, exposant  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * 2 ^ _Exp  
  
##  <a name="a-namelgammaa--lgamma-function"></a><a name="lgamma"></a>lgamma, fonction  
 Calcule le logarithme népérien de la valeur absolue de gamma de l’argument  
  
```  
inline float lgamma(
    float _X,  
    _Out_ int* _Sign) restrict(amp);

 
inline double lgamma(
    double _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Sign`  
 Retourne le signe  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme naturel de la valeur absolue de gamma de l’argument  
  
##  <a name="a-namelgammafa--lgammaf-function"></a><a name="lgammaf"></a>lgammaf, fonction  
 Calcule le logarithme népérien de la valeur absolue de gamma de l’argument  
  
```  
inline float lgammaf(
    float _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Sign`  
 Retourne le signe  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme naturel de la valeur absolue de gamma de l’argument  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log, fonction  
 Calcule le logarithme de base e de l’argument  
  
```  
inline float log(float _X) restrict(amp);

 
inline double log(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme de base e de l’argument  
  
##  <a name="a-namelog10a--log10-function"></a><a name="log10"></a>LOG10 (fonction)  
 Calcule le logarithme en base&10; de l’argument  
  
```  
inline float log10(float _X) restrict(amp);

 
inline double log10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme en base&10; de l’argument  
  
##  <a name="a-namelog10fa--log10f-function"></a><a name="log10f"></a>log10f (fonction)  
 Calcule le logarithme en base&10; de l’argument  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme en base&10; de l’argument  
  
##  <a name="a-namelog1pa--log1p-function"></a><a name="log1p"></a>log1p (fonction)  
 Calcule le logarithme de base e de 1 et de l’argument  
  
```  
inline float log1p(float _X) restrict(amp);

 
inline double log1p(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme de base e 1 et l’argument  
  
##  <a name="a-namelog1pfa--log1pf-function"></a><a name="log1pf"></a>log1pf (fonction)  
 Calcule le logarithme de base e de 1 et de l’argument  
  
```  
inline float log1pf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme de base e 1 et l’argument  
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>LOG2 (fonction)  
 Calcule le logarithme base&2; de l’argument  
  
```  
inline float log2(float _X) restrict(amp);

 
inline double log2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme en base&10; de l’argument  
  
##  <a name="a-namelog2fa--log2f-function"></a><a name="log2f"></a>log2f (fonction)  
 Calcule le logarithme base&2; de l’argument  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme en base&10; de l’argument  
  
##  <a name="a-namelogba--logb-function"></a><a name="logb"></a>logb, fonction  
 Extrait l’exposant de _X, comme une valeur d’entier signé dans un format à virgule flottante  
  
```  
inline float logb(float _X) restrict(amp);

 
inline double logb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie l’exposant de _X signé  
  
##  <a name="a-namelogbfa--logbf-function"></a><a name="logbf"></a>logbf, fonction  
 Extrait l’exposant de _X, comme une valeur d’entier signé dans un format à virgule flottante  
  
```  
inline float logbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie l’exposant de _X signé  
  
##  <a name="a-namelogfa--logf-function"></a><a name="logf"></a>logf, fonction  
 Calcule le logarithme de base e de l’argument  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme de base e de l’argument  
  
##  <a name="a-namemodfa--modf-function"></a><a name="modf"></a>modf, fonction  
 Fractionne l’argument spécifié en une fraction et un nombre entier.  
  
```  
inline float modf(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);

 
inline double modf(
    double _X,  
    _Out_ double* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Iptr`(paramètre de sortie)  
 La partie entière de `_X`, comme une valeur à virgule flottante.  
  
### <a name="return-value"></a>Valeur de retour  
 La fraction signée de `_X`.  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>modff, fonction  
 Fractionne l’argument spécifié en une fraction et un nombre entier.  
  
```  
inline float modff(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Iptr`  
 La partie entière de `_X`, comme une valeur à virgule flottante.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fraction signée de `_X`.  
  
##  <a name="a-namenana--nan-function"></a><a name="nan"></a>NaN (fonction)  
 Retourne une valeur NaN silencieuse  
  
```  
inline double nan(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur NaN silencieuse, si disponible, avec le contenu figurant _X  
  
##  <a name="a-namenanfa--nanf-function"></a><a name="nanf"></a>nanf (fonction)  
 Retourne une valeur NaN silencieuse  
  
```  
inline float nanf(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur NaN silencieuse, si disponible, avec le contenu figurant _X  
  
##  <a name="a-namenearbyinta--nearbyint-function"></a><a name="nearbyint"></a>nearbyint, fonction  
 Arrondit l’argument en une valeur entière dans un format à virgule flottante, à l’aide de la direction d’arrondi actuelle.  
  
```  
inline float nearbyint(float _X) restrict(amp);

 
inline double nearbyint(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur entière arrondie.  
  
##  <a name="a-namenearbyintfa--nearbyintf-function"></a><a name="nearbyintf"></a>nearbyintf, fonction  
 Arrondit l’argument en une valeur entière dans un format à virgule flottante, à l’aide de la direction d’arrondi actuelle.  
  
```  
inline float nearbyintf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur entière arrondie.  
  
##  <a name="a-namenextaftera--nextafter-function"></a><a name="nextafter"></a>nextafter, fonction  
 Déterminer la valeur représentable, dans le type de la fonction, après _X dans la direction de _Y  
  
```  
inline float nextafter(
    float _X,  
    float _Y) restrict(amp);

 
inline double nextafter(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur représentable, dans le type de la fonction, après _X dans la direction de _Y  
  
##  <a name="a-namenextafterfa--nextafterf-function"></a><a name="nextafterf"></a>nextafterf, fonction  
 Déterminer la valeur représentable, dans le type de la fonction, après _X dans la direction de _Y  
  
```  
inline float nextafterf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur représentable, dans le type de la fonction, après _X dans la direction de _Y  
  
##  <a name="a-namephia--phi-function"></a><a name="phi"></a>phi, fonction  
 Retourne la fonction de distribution cumulative de l’argument  
  
```  
inline float phi(float _X) restrict(amp);

 
inline double phi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de distribution cumulative de l’argument  
  
##  <a name="a-namephifa--phif-function"></a><a name="phif"></a>phif, fonction  
 Retourne la fonction de distribution cumulative de l’argument  
  
```  
inline float phif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de distribution cumulative de l’argument  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>Fonction pow  
 Calcule _X élevé à la puissance de _Y  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);

 
inline double pow(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, base  
  
 `_Y`  
 Valeur à virgule flottante, exposant  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namepowfa--powf-function"></a><a name="powf"></a>powf, fonction  
 Calcule _X élevé à la puissance de _Y  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, base  
  
 `_Y`  
 Valeur à virgule flottante, exposant  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameprobita--probit-function"></a><a name="probit"></a>probit, fonction  
 Retourne la fonction de distribution cumulée inverse de l’argument  
  
```  
inline float probit(float _X) restrict(amp);

 
inline double probit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de distribution cumulée inverse de l’argument  
  
##  <a name="a-nameprobitfa--probitf-function"></a><a name="probitf"></a>probitf, fonction  
 Retourne la fonction de distribution cumulée inverse de l’argument  
  
```  
inline float probitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de distribution cumulée inverse de l’argument  
  
##  <a name="a-namercbrta--rcbrt-function"></a><a name="rcbrt"></a>rcbrt, fonction  
 Retourne l’inverse de la racine cubique de l’argument  
  
```  
inline float rcbrt(float _X) restrict(amp);

 
inline double rcbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’inverse de la racine cubique de l’argument  
  
##  <a name="a-namercbrtfa--rcbrtf-function"></a><a name="rcbrtf"></a>rcbrtf, fonction  
 Retourne l’inverse de la racine cubique de l’argument  
  
```  
inline float rcbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’inverse de la racine cubique de l’argument  
  
##  <a name="a-nameremaindera--remainder-function"></a><a name="remainder"></a>Remainder (fonction)  
 Calcule le reste : _X REM _Y  
  
```  
inline float remainder(
    float _X,  
    float _Y) restrict(amp);

 
inline double remainder(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X REM _Y  
  
##  <a name="a-nameremainderfa--remainderf-function"></a><a name="remainderf"></a>remainderf, fonction  
 Calcule le reste : _X REM _Y  
  
```  
inline float remainderf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X REM _Y  
  
##  <a name="a-nameremquoa--remquo-function"></a><a name="remquo"></a>remquo, fonction  
 Calcule le reste du premier argument spécifié divisé par le deuxième argument spécifié. Également calcule le quotient de la mantisse du premier argument spécifié divisée par la mantisse du deuxième argument spécifié et retourne le quotient à l’aide de l’emplacement spécifié dans le troisième argument.  
  
```  
inline float remquo(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);

 
inline double remquo(
    double _X,  
    double _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Le premier argument à virgule flottante.  
  
 `_Y`  
 Le deuxième argument à virgule flottante.  
  
 `_Quo`(paramètre de sortie)  
 L’adresse d’un entier qui est utilisé pour retourner le quotient des bits de fractions de seconde `_X` divisée par les bits de fractions de seconde `_Y`.  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie le reste de `_X` divisé par `_Y`.  
  
##  <a name="a-nameremquofa--remquof-function"></a><a name="remquof"></a>remquof, fonction  
 Calcule le reste du premier argument spécifié divisé par le deuxième argument spécifié. Également calcule le quotient de la mantisse du premier argument spécifié divisée par la mantisse du deuxième argument spécifié et retourne le quotient à l’aide de l’emplacement spécifié dans le troisième argument.  
  
```  
inline float remquof(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Le premier argument à virgule flottante.  
  
 `_Y`  
 Le deuxième argument à virgule flottante.  
  
 `_Quo`(paramètre de sortie)  
 L’adresse d’un entier qui est utilisé pour retourner le quotient des bits de fractions de seconde `_X` divisée par les bits de fractions de seconde `_Y`.  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie le reste de `_X` divisé par `_Y`.  
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>Round (fonction)  
 Arrondit _X à l’entier le plus proche  
  
```  
inline float round(float _X) restrict(amp);

 
inline double round(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’entier le plus proche de _X  
  
##  <a name="a-nameroundfa--roundf-function"></a><a name="roundf"></a>roundf, fonction  
 Arrondit _X à l’entier le plus proche  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’entier le plus proche de _X  
  
##  <a name="a-namersqrta--rsqrt-function"></a><a name="rsqrt"></a>rsqrt, fonction  
 Retourne l’inverse de la racine carrée de l’argument  
  
```  
inline float rsqrt(float _X) restrict(amp);

 
inline double rsqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’inverse de la racine carrée de l’argument  
  
##  <a name="a-namersqrtfa--rsqrtf-function"></a><a name="rsqrtf"></a>rsqrtf, fonction  
 Retourne l’inverse de la racine carrée de l’argument  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’inverse de la racine carrée de l’argument  
  
##  <a name="a-namescalba--scalb-function"></a><a name="scalb"></a>scalb, fonction  
 Multiplie _X par FLT_RADIX à la _Y de l’alimentation  
  
```  
inline float scalb(
    float _X,  
    float _Y) restrict(amp);

 
inline double scalb(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbfa--scalbf-function"></a><a name="scalbf"></a>scalbf, fonction  
 Multiplie _X par FLT_RADIX à la _Y de l’alimentation  
  
```  
inline float scalbf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbna--scalbn-function"></a><a name="scalbn"></a>scalbn, fonction  
 Multiplie _X par FLT_RADIX à la _Y de l’alimentation  
  
```  
inline float scalbn(
    float _X,  
    int _Y) restrict(amp);

 
inline double scalbn(
    double _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbnfa--scalbnf-function"></a><a name="scalbnf"></a>scalbnf, fonction  
 Multiplie _X par FLT_RADIX à la _Y de l’alimentation  
  
```  
inline float scalbnf(
    float _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur entière  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>signbit, fonction  
 Détermine si le signe de _X est négatif  
  
```  
inline int signbit(float _X) restrict(amp);

 
inline int signbit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si le signe _X est négatif  
  
##  <a name="a-namesignbitfa--signbitf-function"></a><a name="signbitf"></a>signbitf, fonction  
 Détermine si le signe de _X est négatif  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si le signe _X est négatif  
  
##  <a name="a-namesina--sin-function"></a><a name="sin"></a>SIN (fonction)  
 Calcule la valeur du sinus de l’argument  
  
```  
inline float sin(float _X) restrict(amp);

 
inline double sin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus de l’argument  
  
##  <a name="a-namesinfa--sinf-function"></a><a name="sinf"></a>Sinf, fonction  
 Calcule la valeur du sinus de l’argument  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus de l’argument  
  
##  <a name="a-namesincosa--sincos-function"></a><a name="sincos"></a>sincos, fonction  
 Calcule le sinus et le cosinus valeur _X  
  
```  
inline void sincos(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);

 
inline void sincos(
    double _X,  
    _Out_ double* _S,  
    _Out_ double* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_S`  
 Retourne la valeur du sinus de _X  
  
 `_C`  
 Retourne la valeur de cosinus de _X  
  
##  <a name="a-namesincosfa--sincosf-function"></a><a name="sincosf"></a>sincosf, fonction  
 Calcule le sinus et le cosinus valeur _X  
  
```  
inline void sincosf(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_S`  
 Retourne la valeur du sinus de _X  
  
 `_C`  
 Retourne la valeur de cosinus de _X  
  
##  <a name="a-namesinha--sinh-function"></a><a name="sinh"></a>sinh (fonction)  
 Calcule la valeur du sinus hyperbolique de l’argument  
  
```  
inline float sinh(float _X) restrict(amp);

 
inline double sinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus hyperbolique de l’argument  
  
##  <a name="a-namesinhfa--sinhf-function"></a><a name="sinhf"></a>sinhf, fonction  
 Calcule la valeur du sinus hyperbolique de l’argument  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus hyperbolique de l’argument  
  
##  <a name="a-namesinpia--sinpi-function"></a><a name="sinpi"></a>sinpi, fonction  
 Calcule la valeur du sinus de pi * _X  
  
```  
inline float sinpi(float _X) restrict(amp);

 
inline double sinpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus de pi * _X  
  
##  <a name="a-namesinpifa--sinpif-function"></a><a name="sinpif"></a>sinpif, fonction  
 Calcule la valeur du sinus de pi * _X  
  
```  
inline float sinpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du sinus de pi * _X  
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>SQRT (fonction)  
 Calcule la racine squre de l’argument  
  
```  
inline float sqrt(float _X) restrict(amp);

 
inline double sqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la racine squre de l’argument  
  
##  <a name="a-namesqrtfa--sqrtf-function"></a><a name="sqrtf"></a>sqrtf, fonction  
 Calcule la racine squre de l’argument  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la racine squre de l’argument  
  
##  <a name="a-nametana--tan-function"></a><a name="tan"></a>tan (fonction)  
 Calcule la valeur de l’argument de tangente  
  
```  
inline float tan(float _X) restrict(amp);

 
inline double tan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de l’argument de tangente  
  
##  <a name="a-nametanfa--tanf-function"></a><a name="tanf"></a>tanf, fonction  
 Calcule la valeur de l’argument de tangente  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de l’argument de tangente  
  
##  <a name="a-nametanha--tanh-function"></a><a name="tanh"></a>TANH, fonction  
 Calcule la valeur de la tangente hyperbolique de l’argument  
  
```  
inline float tanh(float _X) restrict(amp);

 
inline double tanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de la tangente hyperbolique de l’argument  
  
##  <a name="a-nametanhfa--tanhf-function"></a><a name="tanhf"></a>tanhf, fonction  
 Calcule la valeur de la tangente hyperbolique de l’argument  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de la tangente hyperbolique de l’argument  
  
##  <a name="a-nametanpia--tanpi-function"></a><a name="tanpi"></a>tanpi, fonction  
 Calcule la valeur de tangente de pi * _X  
  
```  
inline float tanpi(float _X) restrict(amp);

 
inline double tanpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de tangente de pi * _X  
  
##  <a name="a-nametanpifa--tanpif-function"></a><a name="tanpif"></a>tanpif, fonction  
 Calcule la valeur de tangente de pi * _X  
  
```  
inline float tanpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de tangente de pi * _X  
  
##  <a name="a-nametgammaa--tgamma-function"></a><a name="tgamma"></a>tgamma, fonction  
 Calcule la fonction gamma de _X  
  
```  
inline float tgamma(float _X) restrict(amp);

 
inline double tgamma(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de la fonction gamma de _X  
  
##  <a name="a-nametgammafa--tgammaf-function"></a><a name="tgammaf"></a>tgammaf, fonction  
 Calcule la fonction gamma de _X  
  
```  
inline float tgammaf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de la fonction gamma de _X  
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>trunc, fonction  
 Tronque l’argument pour le composant entier  
  
```  
inline float trunc(float _X) restrict(amp);

 
inline double trunc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la partie entière de l’argument  
  
##  <a name="a-nametruncfa--truncf-function"></a><a name="truncf"></a>truncf, fonction  
 Tronque l’argument pour le composant entier  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la partie entière de l’argument  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::precise_math Namespace](concurrency-precise-math-namespace.md)

