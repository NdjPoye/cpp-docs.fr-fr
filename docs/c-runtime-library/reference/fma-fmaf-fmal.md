---
title: fma, fmaf, fmal | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21eab7d0adc6cf1952f6f26cdda23c885c63a3b3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal
Multiplie deux valeurs, ajoute une troisième valeur, puis arrondit le résultat, sans perdre de précision en raison d’un arrondi intermédiaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Première valeur à multiplier.  
  
 [in] `y`  
 Seconde valeur à multiplier.  
  
 [in] `z`  
 Valeur à ajouter.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `(x * y) + z`. La valeur de retour est ensuite arrondie à l’aide du format d’arrondi actuel.  
  
 Sinon, peut retourner l’une des valeurs suivantes :  
  
|Problème|Retour|  
|-----------|------------|  
|`x` = INFINITY, `y` = 0 ou<br /><br /> `x` = 0, `y` = INFINI|NaN|  
|`x` ou `y` = ± exacte infini, `z` = infini avec le signe opposé|NaN|  
|`x` ou `y` = NaN|NaN|  
|Pas (`x` = 0, `y`= indéfini) et `z` = NaN<br /><br /> Pas (`x` = indéfini, `y` = 0) et `z` = NaN|NaN|  
|Erreur de plage avec dépassement|±HUGE_VAL, ±HUGE_VALF ou ±HUGE_VALL|  
|Erreur de plage avec soupassement|valeur correcte, après arrondi.|  
  
 Les erreurs sont signalées comme indiqué dans [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `fma` qui acceptent et retournent **float** et **long double** types. Dans un programme C, `fma` accepte et retourne toujours un **double**.  
  
 Cette fonction calcule la valeur avec une précision infinie, puis arrondit le résultat final.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`fma`, `fmaf`, `fmal`|\<math.h>|\<cmath>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)