---
title: nearbyint, nearbyintf, nearbyintl | Documents Microsoft
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
- nearbyint
- nearbyintf
- nerabyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d981df622450ef0b52a9b0d81427497a3e180bc
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2018
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl
Arrondit la valeur à virgule flottante spécifiée en un entier et retourne cette valeur dans un format à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Valeur à arrondir.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `x` arrondi à l’entier le plus proche, en utilisant le format d’arrondi actuel tel que défini par fegetround. Sinon, la fonction peut retourner l’une des valeurs suivantes :  
  
|Problème|Retourner|  
|-----------|------------|  
|`x`= ±INFINITY|±Infinity, non modifié|  
|`x` = ±0|±0, non modifié|  
|`x` = NaN|NaN|  
  
 Les erreurs ne sont pas signalées par le biais de [_matherr](../../c-runtime-library/reference/matherr.md) ; plus précisément, cette fonction ne signale pas les exceptions FE_INEXACT.  
  
## <a name="remarks"></a>Notes  
 La principale différence entre cette fonction et `rint` est qu’elle ne déclenche pas l’exception de virgule flottante inexacte.  
  
 Étant donné que les valeurs à virgule flottante maximales sont des entiers exacts, cette fonction ne provoque jamais de dépassement par elle-même. Cependant, la sortie peut dépasser la valeur de retour, selon la version de la fonction que vous utilisez.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`nearbyint`,                `nearbyintf`,  `nearbyintl`|\<math.h>|\<cmath>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)