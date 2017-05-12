---
title: fdim, fdimf, fdiml | Microsoft Docs
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
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs:
- C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: f13291a00b97c319ebe69bce6939a95e6c022fd8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml
Détermine la différence positive entre les première et deuxième valeurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Première valeur.  
  
 [in] `y`  
 Seconde valeur.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la différence positive entre `x` et `y` :  
  
|Valeur de retour|Scénario|  
|------------------|--------------|  
|x-y|Si x > y|  
|0|Si x <= y|  
  
 Sinon, peut retourner l’une des erreurs suivantes :  
  
|Problème|Retourner|  
|-----------|------------|  
|Erreur de plage avec dépassement|+HUGE_VAL, +HUGE_VALF ou +HUGE_VALL|  
|Erreur de plage avec soupassement|valeur correcte (après arrondi)|  
|`x` ou `y` est NaN|NaN|  
  
 Les erreurs sont signalées comme indiqué dans [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `fdim` qui acceptent et retournent des types double long et à virgule flottante. Dans un programme C, `fdim` accepte et retourne toujours un double.  
  
 À l’exception de la gestion de la valeur NaN, cette fonction est équivalente à `fmax(x - y, 0)`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`fdim`, `fdimf`, `fdiml`|\<math.h>|\<cmath>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs, labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)
