---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs:
- C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4fe078e00b28f09284f3b91ad93ee1393bea108
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
Retourne la valeur à virgule flottante représentable suivante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante de départ.  
  
 `y`  
 Valeur à virgule flottante d’arrivée.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la valeur à virgule flottante représentable suivante du type de retour après `x` dans la direction de `y`. Si `x`=`y`, la fonction retourne `y`, converti dans le type de retour, sans qu’aucune exception ne soit déclenchée. Si `x` est différent de `y`, le résultat est une valeur dénormalisée ou égale à zéro, les états d’exception de virgule flottante FE_UNDERFLOW et FE_INEXACT sont définis, puis le résultat correct est retourné. Si `x` ou `y` est un NaN, la valeur de retour est l’un des NaN d’entrée. Si `x` est fini et que le résultat est infini ou non représentable dans le type, une valeur infinie ou NaN correctement signée est retournée, les états d’exception de virgule flottante FE_OVERFLOW et FE_INEXACT sont définis, puis `errno` prend la valeur ERANGE.  
  
## <a name="remarks"></a>Notes  
 Les familles des fonctions `nextafter` et `nexttoward` sont équivalentes, à l’exception du type de paramètre de `y`. Si `x` et `y` sont égaux, la valeur retournée est `y` convertie dans le type de retour.  
  
 Sachant que C++ autorise la surcharge, si vous incluez \<cmath>, vous pouvez appeler des surcharges de `nextafter` et `nexttoward` qui retournent les types `float` et `long double`. Dans un programme C, `nextafter` et `nexttoward` retournent toujours `double`.  
  
 Les fonctions `_nextafter` et `_nextafterf` sont spécifiques à Microsoft. La fonction `_nextafterf` est n’est disponible que quand elle est compilée pour x64.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis (C)|En-tête requis (C++)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h>|\<math.h> ou \<cmath>|  
|`_nextafter`|\<float.h>|\<float.h> ou \<cfloat>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)