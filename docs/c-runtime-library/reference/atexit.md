---
title: atexit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- atexit
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
- atexit
dev_langs:
- C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6d0d85ffc7f3ed71a26a947dd66c710e76388e96
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="atexit"></a>atexit
Traite la fonction spécifiée en sortie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `func`  
 Fonction à appeler.  
  
## <a name="return-value"></a>Valeur de retour  
 `atexit` retourne 0 en cas de réussite, ou une valeur différente de zéro si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 La fonction `atexit` est passée à l’adresse d’une fonction (`func`) à appeler quand le programme se termine normalement. Les appels successifs à `atexit` créent un registre des fonctions qui sont exécutées dans l’ordre « dernier entré, premier sorti » (LIFO). Les fonctions transmises à `atexit` ne peuvent pas prendre de paramètres. `atexit` et `_onexit` utilisent le tas pour conserver le registre des fonctions. Le nombre de fonctions pouvant être enregistrées n’est donc limité que par la mémoire de tas.  
  
 Le code dans la fonction `atexit` ne doit pas contenir de dépendance vis-à-vis d’une DLL ayant pu être déchargée avant l’appel de la fonction `atexit`.  
  
 Pour générer une application compatible ANSI, utilisez la fonction `atexit` compatible avec la norme ANSI (au lieu de la fonction `_onexit` similaire).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`atexit`|\<stdlib.h>|  
  
## <a name="example"></a>Exemple  
 Ce programme place quatre fonctions sur la pile de fonctions à exécuter quand `atexit` est appelé. Quand le programme s’arrête, ces programmes sont exécutés dans l’ordre « dernier entré, premier sorti ».  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
```Output  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)
