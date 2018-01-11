---
title: trunc, truncf, truncl | Microsoft Docs
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
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
dev_langs: C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 911636e4fa843afa1220dc99e1f679d5bfe88d7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl
Détermine l’entier le plus proche dont la valeur est inférieure ou égale à la valeur à virgule flottante spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Valeur à tronquer.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne une valeur entière de `x`, arrondie vers zéro.  
  
 Sinon, peut retourner l’une des valeurs suivantes :  
  
|Problème|Retourner|  
|-----------|------------|  
|`x`= ±INFINITY|x|  
|`x` =  ±0|x|  
|`x` = NaN|NaN|  
  
 Les erreurs sont signalées comme indiqué dans [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `trunc` qui acceptent et retournent des types double long et à virgule flottante. Dans un programme C, `trunc` accepte et retourne toujours un type double.  
  
 Comme les valeurs à virgule flottante les plus grandes sont des entiers exacts, cette fonction ne provoque pas de dépassement de capacité. Cependant, vous pouvez causer le dépassement de capacité de la fonction en retournant une valeur sous dans un type entier.  
  
 Vous pouvez aussi arrondir vers le bas en convertissant de manière implicite une valeur à virgule flottante en entier ; cependant, cette opération se limite aux valeurs qui peuvent être stockées dans le type cible.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`trunc`,                `truncf`,  `truncl`|\<math.h>|\<cmath>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)