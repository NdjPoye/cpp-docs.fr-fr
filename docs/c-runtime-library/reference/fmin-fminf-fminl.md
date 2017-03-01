---
title: Fmax, fminf, fminl | Documents Microsoft
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
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: 8953e3bd81158ce183e1abb5dfa969164c1f9ced
ms.openlocfilehash: b7fd6a2b91c1bc7cd973d2ac60f2d6fc39d322bb
ms.lasthandoff: 02/24/2017

---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl
Détermine la plus petite de deux valeurs spécifiées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Première valeur à comparer.  
  
 `y`  
 Deuxième valeur à comparer.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne la plus petite valeur (`x` ou `y`).  
  
|Entrée|Résultat|  
|-----------|------------|  
|`x` est NaN|`y`|  
|`y` est NaN|`x`|  
|`x` et `y` sont NaN|NaN|  
  
 La fonction n’entraîne pas l’appel de [_matherr](../../c-runtime-library/reference/matherr.md), d’exceptions de virgule flottante ou de modification de la valeur de `errno`.  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `fmin` qui acceptent et retournent des types double long et à virgule flottante. Dans un programme C, `fmin` accepte et retourne toujours un double.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`fmin`, `fminf`, `fminl`|C : \<math.h><br />C++ : \<math.h> ou \<cmath>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)  
