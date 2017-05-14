---
title: ceil, ceilf, ceill | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ceilf
- ceil
- ceill
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
- ceil
- ceilf
- ceill
dev_langs:
- C++
helpviewer_keywords:
- calculating value ceilings
- ceill function
- ceil function
- ceilf function
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 1fd4b888c8fc332c07aed62af03b340864dfe3bf
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ceil-ceilf-ceill"></a>ceil, ceilf, ceill
Calcule le plafond d’une valeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
## <a name="return-value"></a>Valeur de retour  
 Les fonctions `ceil` retournent une valeur à virgule flottante qui représente le plus petit entier supérieur ou égal à `x`. Aucun retour d'erreur.  
  
|Entrée|Exception SEH|Exception{b> <b}Matherr|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|aucun|`_DOMAIN`|  
  
 `ceil` présente une implémentation qui utilise SSE2 (Streaming SIMD Extensions 2). Pour plus d’informations sur l’utilisation de l’implémentation SSE2 et sur les restrictions qui s’y rattachent, consultez [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `ceil`. Dans un programme C, `ceil` accepte et retourne toujours un double.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`ceil`, `ceilf`, `ceill`|\<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [floor](../../c-runtime-library/reference/floor-floorf-floorl.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)
