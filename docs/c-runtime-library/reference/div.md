---
title: div | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: div
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: div
dev_langs: C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a942c3414fa7801912de59ec41fd6477d7c19f2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="div"></a>div
Calcule le quotient et le reste de deux valeurs entières.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### <a name="parameters"></a>Paramètres  
 `numer`  
 Numérateur.  
  
 `denom`  
 Dénominateur.  
  
## <a name="return-value"></a>Valeur de retour  
 Quand la fonction `div` est appelée à l’aide d’arguments de type `int`, elle retourne une structure de type `div_t`, qui comprend le quotient et le reste. La valeur de retour de la surcharge avec des arguments de type `long` est `ldiv_t`. `div_t` et `ldiv_t` sont définis dans STDLIB.H.  
  
## <a name="remarks"></a>Notes  
 La fonction `div` divise `numer` par `denom`, calculant ainsi le quotient et le reste. La structure [div_t](../../c-runtime-library/standard-types.md) contient le quotient, `int quot`, et le reste, `int rem`. Le signe du quotient est identique à celui du quotient mathématique. Sa valeur absolue est le plus grand entier qui est inférieur à la valeur absolue du quotient mathématique. Si le dénominateur est 0, le programme se termine par un message d’erreur.  
  
 Les surcharges qui acceptent des arguments de type `long` ou `long long` sont uniquement disponibles pour du code C++. Le type de retour [ldiv_t](../../c-runtime-library/standard-types.md) contient les membres `long quot` et `long rem`, tandis que le type de retour [lldiv_t](../../c-runtime-library/standard-types.md) contient les membres `long long quot` et `long long rem`, qui ont la même signification que les membres de `div_t`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`div`|\<stdlib.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
```Output  
x is 876, y is 13  
The quotient is 67, and the remainder is 5  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)