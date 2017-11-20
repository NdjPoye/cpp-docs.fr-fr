---
title: modf, modff, modfl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
dev_langs: C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72568970159c1b334232bb81f0295d829a5221af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl
Scinde une valeur à virgule flottante en une partie fractionnaire et une partie entière.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *x*  
 Valeur à virgule flottante.  
  
 `intptr`  
 Pointeur désignant la partie entière stockée.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette fonction retourne la partie fractionnaire signée de *x*. Aucun retour d'erreur.  
  
## <a name="remarks"></a>Notes  
 Les fonctions `modf` scindent la valeur à virgule flottante `x` en une partie fractionnaire et une partie entière, chacune d’elles ayant le même signe que `x`. La partie fractionnaire signée de `x` est retournée. La partie entière est stockée en tant que valeur à virgule flottante dans `intptr.`  
  
 `modf` présente une implémentation qui utilise SSE2 (Streaming SIMD Extensions 2). Consultez [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) pour plus d’informations sur l’utilisation de l’implémentation SSE2 et sur les restrictions qui s’y rattachent.  
  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `modf` qui acceptent et retournent des paramètres `float` ou `long double`. Dans un programme C, `modf` prend deux valeurs doubles et en retourne une systématiquement.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`modf`, `modff`, `modfl`|C : \<math.h><br /><br /> C++ : \<cmath> ou \<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)