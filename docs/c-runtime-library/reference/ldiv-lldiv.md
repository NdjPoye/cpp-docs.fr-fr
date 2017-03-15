---
title: ldiv, lldiv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ldiv
- lldiv
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
f1_keywords:
- ldiv
- lldiv
dev_langs:
- C++
helpviewer_keywords:
- ldiv function
- lldiv function
- quotients, computing
- computing remainders
- remainder computing
- computing quotients
ms.assetid: 68ab5d83-27a4-479c-9d52-d055eb139eca
caps.latest.revision: 12
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
ms.openlocfilehash: 682b46a134eacbc7e9482ac41e407d4690810eb0
ms.lasthandoff: 02/24/2017

---
# <a name="ldiv-lldiv"></a>ldiv, lldiv
Calcule le quotient et le reste de deux entiers en une seule opération.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ldiv_t ldiv(  
   long numer,  
   long denom   
);  
lldiv_t lldiv(  
   long long numer,  
   long long denom   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `numer`  
 Numérateur.  
  
 `denom`  
 Dénominateur.  
  
## <a name="return-value"></a>Valeur de retour  
 `ldiv` retourne une structure de type [ldiv_t](../../c-runtime-library/standard-types.md) qui comprend à la fois le quotient et le reste. `lldiv` retourne une structure de type [lldiv_t](../../c-runtime-library/standard-types.md) qui comprend à la fois le quotient et le reste.  
  
## <a name="remarks"></a>Notes  
 Les fonctions `ldiv` et `lldiv` divisent `numer` par `denom`, calculant ainsi le quotient et le reste. Le signe du quotient est identique à celui du quotient mathématique. La valeur absolue du quotient est le plus grand entier qui est inférieur à la valeur absolue du quotient mathématique. Si le dénominateur est 0, le programme se termine par un message d’erreur. `ldiv` et `lldiv` sont identiques à `div`, à ceci près que les arguments de `ldiv` et les membres de la structure retournée sont tous de type `long`, tandis que les arguments de `lldiv` et les membres de la structure retournée sont de type `long long`.  
  
 Les structures `ldiv_t` et `lldiv_t` sont définies dans \<stdlib.h>.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`ldiv`, `lldiv`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_ldiv.c  
  
#include <stdlib.h>  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   long x = 5149627, y = 234879;  
   ldiv_t div_result;  
  
   div_result = ldiv( x, y );  
   printf( "For %ld / %ld, the quotient is ", x, y );  
   printf( "%ld, and the remainder is %ld\n",   
            div_result.quot, div_result.rem );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
For 5149627 / 234879, the quotient is 21, and the remainder is 217168  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)
