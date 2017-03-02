---
title: "Fonctions d’espace de noms Concurrency::fast_math | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4a01f48a7d087281ab1e9222d1077e92ab8b0d6c
ms.openlocfilehash: 0545a57c492f5c1872c71c04c99b54f86b644102
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace-functions"></a>Fonctions d’espace de noms Concurrency::fast_math
||||  
|-|-|-|  
|[ACOS (fonction)](#acos)|[acosf, fonction](#acosf)|[ASIN (fonction)](#asin)|  
|[asinf, fonction](#asinf)|[ATAN (fonction)](#atan)|[ATAN2 (fonction)](#atan2)|  
|[atan2f (fonction)](#atan2f)|[atanf, fonction](#atanf)|[ceil (fonction)](#ceil)|  
|[ceilf, fonction](#ceilf)|[COS (fonction)](#cos)|[cosf, fonction](#cosf)|  
|[COSH (fonction)](#cosh)|[coshf, fonction](#coshf)|[EXP (fonction)](#exp)|  
|[exp2 (fonction)](#exp2)|[exp2f (fonction)](#exp2f)|[expf, fonction](#expf)|  
|[fabs, fonction](#fabs)|[fabsf, fonction](#fabsf)|[Floor, fonction](#floor)|  
|[floorf, fonction](#floorf)|[Fmax, fonction](#fmax)|[fmaxf, fonction](#fmaxf)|  
|[fmin, fonction](#fmin)|[fminf, fonction](#fminf)|[fmod, fonction](#fmod)|  
|[fmodf, fonction](#fmodf)|[frexp, fonction](#frexp)|[frexpf, fonction](#frexpf)|  
|[isFinite, fonction](#isfinite)|[isinf, fonction](#isinf)|[isNaN (fonction)](#isnan)|  
|[ldexp, fonction](#ldexp)|[ldexpf, fonction](#ldexpf)|[log, fonction](#log)|  
|[LOG10 (fonction)](#log10)|[log10f (fonction)](#log10f)|[LOG2 (fonction)](#log2)|  
|[log2f (fonction)](#log2f)|[logf, fonction](#logf)|[modf, fonction](#modf)|  
|[modff, fonction](#modff)|[Fonction pow](#pow)|[powf, fonction](#powf)|  
|[Round (fonction)](#round)|[roundf, fonction](#roundf)|[rsqrt, fonction](#rsqrt)|  
|[rsqrtf, fonction](#rsqrtf)|[signbit, fonction](#signbit)|[signbitf, fonction](#signbitf)|  
|[SIN (fonction)](#sin)|[sincos, fonction](#sincos)|[sincosf, fonction](#sincosf)|  
|[Sinf, fonction](#sinf)|[sinh (fonction)](#sinh)|[sinhf, fonction](#sinhf)|  
|[SQRT (fonction)](#sqrt)|[sqrtf, fonction](#sqrtf)|[tan (fonction)](#tan)|  
|[tanf, fonction](#tanf)|[TANH, fonction](#tanh)|[tanhf, fonction](#tanhf)|  
|[trunc, fonction](#trunc)|[truncf, fonction](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>ACOS (fonction)  
 Calcule l’arc cosinus de l’argument  
  
```  
inline float acos(float _X) restrict(amp);
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
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>ASIN (fonction)  
 Calcule l’arc sinus de l’argument  
  
```  
inline float asin(float _X) restrict(amp);
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
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>ATAN (fonction)  
 Calcule l’arc tangente de l’argument  
  
```  
inline float atan(float _X) restrict(amp);
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
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil (fonction)  
 Calcule le plafond de l’argument  
  
```  
inline float ceil(float _X) restrict(amp);
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
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>COS (fonction)   
 Calcule le cosinus de l’argument  
  
```  
inline float cos(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de cosinus hyperbolique de l’argument  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>EXP (fonction)  
 Calcule la valeur exponentielle de l’argument de base e  
  
```  
inline float exp(float _X) restrict(amp);
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
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>fabs, fonction  
 Retourne la valeur absolue de l’argument  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
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
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>Floor, fonction  
 Calcule le plancher de l’argument  
  
```  
inline float floor(float _X) restrict(amp);
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
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>Fmax, fonction  
 Déterminer la valeur numérique maximale des arguments  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
 `_Y`  
 Valeur entière  
  
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
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur entière  
  
 `_Y`  
 Valeur entière  
  
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
  
##  <a name="a-namefmoda--fmod-function"></a><a name="fmod"></a>fmod, fonction  
 Calcule le reste à virgule flottante de _X/_Y  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le reste à virgule flottante de _X/_Y  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>fmodf, fonction  
 Calcule le reste à virgule flottante de _X/_Y.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Y`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le reste à virgule flottante de _X/_Y  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>frexp, fonction  
 Obtient la mantisse et l’exposant de _X  
  
```  
inline float frexp(
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
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>isFinite, fonction  
 Détermine si l’argument a une valeur finie  
  
```  
inline int isfinite(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si et seulement si l’argument a une valeur NaN  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>ldexp, fonction  
 Calcule le nombre réel de la mantisse et exposant  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, mentissa  
  
 `_Exp`  
 Exposant entier  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * 2 ^ _Exp  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>ldexpf, fonction  
 Calcule le nombre réel de la mantisse et exposant  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, mentissa  
  
 `_Exp`  
 Exposant entier  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne _X * 2 ^ _Exp  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log, fonction  
 Calcule le logarithme de base e de l’argument  
  
```  
inline float log(float _X) restrict(amp);
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
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>LOG2 (fonction)  
 Calcule le logarithme base&2; de l’argument  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le logarithme base&2; de l’argument  
  
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
 Fractionne _X en une fraction et un nombre entier.  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Ip`  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fraction signée de _X  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>modff, fonction  
 Fractionne _X en une fraction et un nombre entier.  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante  
  
 `_Ip`  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la fraction signée de _X  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>Fonction pow  
 Calcule _X élevé à la puissance de _Y  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_X`  
 Valeur à virgule flottante, base  
  
 `_Y`  
 Valeur à virgule flottante, exposant  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de _X élevé à la puissance de _Y  
  
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
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>Round (fonction)  
 Arrondit _X à l’entier le plus proche  
  
```  
inline float round(float _X) restrict(amp);
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
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>signbit, fonction  
 Détermine si le signe de _X est négatif  
  
```  
inline int signbit(float _X) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>SQRT (fonction)  
 Calcule la racine squre de l’argument  
  
```  
inline float sqrt(float _X) restrict(amp);
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
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>trunc, fonction  
 Tronque l’argument pour le composant entier  
  
```  
inline float trunc(float _X) restrict(amp);
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
 [Concurrency::fast_math Namespace](concurrency-fast-math-namespace.md)

