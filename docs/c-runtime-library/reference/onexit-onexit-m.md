---
title: _onexit, _onexit_m | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _onexit
- _onexit_m
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
apitype: DLLExport
f1_keywords:
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 50070672e990333073f5ad7f7ba604110c3a3cfa
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m
Inscrit une routine à appeler au moment de la sortie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `function`  
 Pointeur désignant une fonction à appeler à la sortie.  
  
## <a name="return-value"></a>Valeur de retour  
 `_onexit` retourne un pointeur vers la fonction en cas de réussite ou la valeur `NULL` en l’absence d’espace pour stocker le pointeur de la fonction.  
  
## <a name="remarks"></a>Notes  
 La fonction `_onexit` est transmise à l’adresse de la fonction (`function`) à appeler quand le programme se termine normalement. Les appels successifs à `_onexit` créent un registre des fonctions qui sont exécutées selon l’ordre du dernier entré, premier sorti (LIFO). Les fonctions transmises à `_onexit` ne peuvent pas prendre de paramètres.  
  
 Dans le cas où la fonction `_onexit` est appelée à partir d’une DLL, les routines inscrites auprès de `_onexit` s’exécutent lors du déchargement de la DLL après que `DllMain` est appelé avec DLL_PROCESS_DETACH.  
  
 `_onexit` est une extension Microsoft. Pour la portabilité ANSI, utilisez [atexit](../../c-runtime-library/reference/atexit.md). La version `_onexit_m` de la fonction est destinée à une utilisation en mode mixte.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_onexit`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [__dllonexit](../../c-runtime-library/dllonexit.md)
