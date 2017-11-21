---
title: nearbyint, nearbyintf, nearbyintl1 | Microsoft Docs
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
dev_langs: C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 205381e315cf703a9fded4b24812a32c4aef4a9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
|`x` = ±INFINITY|±INFINITY, non modifié|  
|`x` = ±0|±0, non modifié|  
|`x` = NaN|NaN|  
  
 Les erreurs ne sont pas signalées par le biais de [_matherr](../../c-runtime-library/reference/matherr.md) ; plus précisément, cette fonction ne signale pas les exceptions FE_INEXACT.  
  
## <a name="remarks"></a>Notes  
 La principale différence entre cette fonction et `rint` est qu’elle ne déclenche pas l’exception de virgule flottante inexacte.  
  
 Étant donné que les valeurs à virgule flottante maximales sont des entiers exacts, cette fonction ne provoque jamais de dépassement par elle-même. Cependant, la sortie peut dépasser la valeur de retour, selon la version de la fonction que vous utilisez.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`nearbyint`,                `nearbyintf`,  `nearbyintl`|\<math.h>|\<cmath>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)