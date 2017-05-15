---
title: log1p, log1pf, log1pl2 | Microsoft Docs
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
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: 7
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
ms.openlocfilehash: 99525c8b711d0774fa2b3132505a2cdbb21d5569
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl
Calcule le logarithme népérien de 1 plus la valeur spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Argument à virgule flottante.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne le logarithme népérien (base e) de (`x`+1).  
  
 Sinon, peut retourner l’une des valeurs suivantes :  
  
|Entrée|Résultat|Exception SEH|errno|  
|-----------|------------|-------------------|-----------|  
|+inf|+inf|||  
|Nombres dénormalisés|Identique à l’entrée|UNDERFLOW||  
|±0|Identique à l’entrée|||  
|-1|-inf|DIVBYZERO|ERANGE|  
|< -1|nan|INVALID|EDOM|  
|-inf|nan|INVALID|EDOM|  
|±SNaN|Identique à l’entrée|INVALID||  
|±QNaN, indéfini|Identique à l’entrée|||  
  
 `errno` prend la valeur ERANGE si `x` est égal à -1. Le `errno` a la valeur EDOM si `x` < -1.  
  
## <a name="remarks"></a>Remarques  
 Les fonctions `log1p` peuvent être plus précises que l’utilisation de log(`x`+1) si x est proche de 0.  
  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `log1p` qui acceptent et retournent des types double long et à virgule flottante. Dans un programme C, `log1p` accepte et retourne toujours un double.  
  
 Si `x` est un nombre naturel, cette fonction retourne le logarithme de la factorielle de (`x`-1).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`log1p`,                `log1pf`,  `log1pl`|\<math.h>|\<cmath>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)
