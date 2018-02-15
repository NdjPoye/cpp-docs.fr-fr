---
title: isnan, _isnan, _isnanf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10d0997b1a6b304634c612f0f1615a059fd812b2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf
Teste si une valeur à virgule flottante n’est pas un nombre (NAN).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### <a name="parameters"></a>Paramètres  
 *x*  
 Valeur à virgule flottante à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 En C, la macro `isnan` et les fonctions `_isnan` et `_isnanf` retournent une valeur différente de zéro si l’argument `x` est une valeur NAN ; sinon, elles retournent 0.  
  
 En C++, les fonctions de modèle `isnan` retournent `true` si l’argument `x` est une valeur NAN ; sinon, elles retournent `false`.  
  
## <a name="remarks"></a>Notes  
 La macro `isnan` C et les fonctions `_isnan` et `_isnanf` testent la valeur à virgule flottante *x* et retournent une valeur différente de zéro si *x* est une valeur NAN (valeur non numérique). Une valeur NAN est générée quand le résultat d’une opération à virgule flottante ne peut pas être représenté dans un format à virgule flottante IEEE-754 pour le type spécifié. Pour plus d’informations sur la représentation d’une valeur NAN dans la sortie, consultez [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Durant sa compilation en C++, la macro `isnan` n’est pas définie. Une fonction de modèle `isnan` est définie à la place. Elle retourne une valeur de type `bool` au lieu d’un entier.  
  
 Les fonctions `_isnan` et `_isnanf` sont propres à Microsoft. La fonction `_isnanf` n’est disponible que quand elle est compilée pour x64.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis (C)|En-tête requis (C++)|  
|-------------|---------------------------|-------------------------------|  
|`isnan`, `_isnanf`|\<math.h>|\<math.h> ou \<cmath>|  
|`_isnan`|\<float.h>|\<float.h> ou \<cfloat>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_finite, _finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)