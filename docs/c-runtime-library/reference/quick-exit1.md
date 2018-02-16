---
title: quick_exit1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- quick_exit
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- quick_exit
- process/quick_exit
- stdlib/quick_exit
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30c8ae3290ac4b15247b88b0b2201634e42b560b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="quickexit"></a>quick_exit
Provoque l’arrêt normal du programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__declspec(noreturn) void quick_exit(  
    int status  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 status  
 Code d’état à retourner à l’environnement hôte.  
  
## <a name="return-value"></a>Valeur de retour  
 La fonction `quick_exit` ne peut pas retourner à son appelant.  
  
## <a name="remarks"></a>Notes  
 La fonction `quick_exit` provoque l’arrêt normal du programme. Elle n’appelle aucune fonction inscrite par `atexit`, `_onexit` ou manipulateurs de signaux inscrits par la fonction `signal` . Le comportement n’est pas défini si `quick_exit` est appelée plusieurs fois ou si la fonction `exit` est également appelée.  
  
 La fonction `quick_exit` appelle, dans l’ordre FIFO (dernier entré, premier sorti), les fonctions inscrites par `at_quick_exit`, sauf celles déjà appelées lorsque la fonction a été inscrite.  Le comportement n’est pas défini si un appel à [longjmp](../../c-runtime-library/reference/longjmp.md) est effectué pendant un appel à une fonction inscrite qui terminerait l’appel à la fonction.  
  
 Une fois que les fonctions inscrites ont été appelées, `quick_exit` appelle `_Exit` à l’aide de la valeur `status` pour rendre le contrôle à l’environnement hôte.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`quick_exit`|\<process.h> ou \<stdlib.h>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)