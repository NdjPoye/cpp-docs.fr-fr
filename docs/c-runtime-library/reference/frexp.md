---
title: frexp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- frexp
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
- frexp
- _frexpl
dev_langs:
- C++
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1f255fbc6eb63374a8651a11abaf0266ed9cfd6f
ms.lasthandoff: 02/24/2017

---
# <a name="frexp"></a>frexp
Obtient la mantisse et l’exposant d’un nombre à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
 `expptr`  
 Pointeur désignant l’exposant entier stocké.  
  
## <a name="return-value"></a>Valeur de retour  
 `frexp` retourne la mantisse. Si `x` a la valeur 0, la fonction retourne 0 pour la mantisse et l’exposant. Si `expptr` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte à `errno` la valeur `EINVAL` et retourne 0.  
  
## <a name="remarks"></a>Notes  
 La fonction `frexp` décompose la valeur à virgule flottante (`x`) en une mantisse (`m`) et un exposant (`n`), de manière à ce que la valeur absolue de `m` soit supérieure ou égale à 0,5 et inférieure à 1,0 et que soit respectée l’égalité `x` = `m`*2<sup>n</sup>. L’exposant entier `n` est stocké à l’emplacement désigné par `expptr`.  
  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `frexp`. Dans un programme C, `frexp` accepte un double et un entier et retourne un double systématiquement.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`frexp`|\<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
```Output  
frexp( 16.400000, &n ) = 0.512500, n = 5  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)
