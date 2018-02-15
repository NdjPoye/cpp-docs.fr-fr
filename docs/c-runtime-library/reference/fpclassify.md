---
title: fpclassify | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81a2c9c5237d455908e1d0e4f58bff87418a7f8b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fpclassify"></a>fpclassify
Retourne la classification à virgule flottante de l’argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 `fpclassify` retourne une valeur entière qui indique la classification à virgule flottante de l’argument `x`. Ce tableau montre les valeurs possibles retournées par `fpclassify`, définies dans \<math.h>.  
  
|Value|Description|  
|-----------|-----------------|  
|`FP_NAN`|NaN silencieux, signalant ou indéterminé|  
|`FP_INFINITE`|Infini positif ou négatif|  
|`FP_NORMAL`|Valeur non nulle normalisée positive ou négative|  
|`FP_SUBNORMAL`|Valeur dénormalisée positive ou négative|  
|`FP_ZERO`|Valeur nulle positive ou négative|  
  
## <a name="remarks"></a>Notes  
 En C, `fpclassify` est une macro ; en C++, `fpclassify` est une fonction surchargée à l’aide des types d’arguments de `float`, `double` ou `long double`. Dans les deux cas, la valeur retournée dépend du type effectif de l’expression d’argument et non d’une représentation intermédiaire. Par exemple, une valeur `double` ou `long double` normale peut devenir une valeur infinie, dénormalisée ou nulle quand elle est convertie en un `float`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction/macro|En-tête requis (C)|En-tête requis (C++)|  
|---------------------|---------------------------|-------------------------------|  
|`fpclassify`|\<math.h>|\<math.h> ou \<cmath>|  
  
 La macro `fpclassify` et les fonctions `fpclassify` sont conformes aux spécifications C99 et C++11. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)