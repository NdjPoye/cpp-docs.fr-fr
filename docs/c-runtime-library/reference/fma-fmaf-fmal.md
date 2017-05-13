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
ms.topic: article
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 59238cf511be936b0d882c2f00320ee7422904e0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

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
|`x` = INFINITY, `y` = 0 ou<br /><br /> `x` = 0, `y` = INFINITY|NaN|  
|`x` ou `y` = exact ± INFINITY, `z` = INFINITY avec le signe opposé|NaN|  
|`x` ou `y` = NaN|NaN|  
|Pas (`x` = 0, `y`= indéfini) et `z` = NaN<br /><br /> Pas (`x` = indéfini, `y` = 0) et `z` = NaN|NaN|  
|Erreur de plage avec dépassement|±HUGE_VAL, ±HUGE_VALF ou ±HUGE_VALL|  
|Erreur de plage avec soupassement|valeur correcte, après arrondi.|  
  
 Les erreurs sont signalées comme indiqué dans [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Remarques  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `fma` qui acceptent et retournent **float** et **long double** types. Dans un programme C, `fma` accepte et retourne toujours un **double**.  
  
 Cette fonction calcule la valeur avec une précision infinie, puis arrondit le résultat final.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`fma`, `fmaf`, `fmal`|\<math.h>|\<cmath>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)
