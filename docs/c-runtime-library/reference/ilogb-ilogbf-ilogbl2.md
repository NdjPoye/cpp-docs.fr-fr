---
title: ilogb, ilogbf, ilogbl2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ecf7f9bb38cdd844514001126a98bced67617e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl
Récupère un entier qui représente l’exposant en base 2 non biaisé de la valeur spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Valeur spécifiée.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne l’exposant en base 2 de `x` sous forme de valeur `int` signée.  
  
 Sinon, retourne une des valeurs suivantes, définies dans \<math.h> :  
  
|Entrée|Résultat|  
|-----------|------------|  
|±0|FP_ILOGB0|  
|±inf, ±nan, indéterminée|FP_ILOGBNAN|  
  
 Les erreurs sont signalées comme indiqué dans [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `ilogb` qui acceptent et retournent des types double long et à virgule flottante. Dans un programme C, `ilogb` accepte et retourne toujours un double.  
  
 Appeler cette fonction revient à appeler la fonction `logb` équivalente, puis à effectuer un cast de la valeur de retour vers `int`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête C|En-tête C++|  
|-------------|--------------|------------------|  
|`ilogb`,                `ilogbf`,  `ilogbl`|\<math.h>|\<cmath>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, _logb, _logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)