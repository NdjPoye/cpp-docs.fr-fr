---
title: _Cmulcr, _FCmulcr, _LCmulcr | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cmulcr
- _FCmulcr
- _LCmulcr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
dev_langs:
- C++
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1de966b1eb5bd48d4a3120d23c9ffc0de647956
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2018
---
# <a name="cmulcr-fcmulcr-lcmulcr"></a>_Cmulcr, _FCmulcr, _LCmulcr

Multiplie un nombre complexe par un nombre à virgule flottante.

## <a name="syntax"></a>Syntaxe

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>Paramètres

*x*<br/>
Un des opérandes complexes à multiplier.

*y*<br/>
L’opérande à virgule flottante à multiplier.

## <a name="return-value"></a>Valeur de retour

A **_Dcomplex**, **_Fcomplex**, ou **_Lcomplex** structure qui représente le produit complexe du nombre complexe *x* et nombre à virgule flaoting *y*.

## <a name="remarks"></a>Notes

Étant donné que les opérateurs arithmétiques intégrés ne fonctionnent pas sur l’implémentation Microsoft de types complexes, le **_Cmulcr**, **_FCmulcr**, et **_LCmulcr** fonctions simplifier la multiplication de types complexes par les types à virgule flottante.

## <a name="requirements"></a>Spécifications

|Routine|En-tête C|En-tête C++|
|-------------|--------------|------------------|
|`_Cmulcr`,`_FCmulcr`, `_LCmulcr`|\<complex.h>|\<ccomplex>|

Ces fonctions sont spécifiques à Microsoft. Les types **_Dcomplex**, **_Fcomplex**, et **_Lcomplex** sont équivalents spécifiques à Microsoft pour les types natifs C99 non implémentées **_Complex double** , **float _Complex**, et **_Complex long double**, respectivement. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Voir aussi

[Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](../../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](../../c-runtime-library/reference/cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)<br/>
[creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)<br/>
