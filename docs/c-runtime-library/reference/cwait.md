---
title: _cwait | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cwait
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cwait
dev_langs:
- C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 23
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 8d5cfdb53b5aab8e6b0404b84de87ba24ee57597
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="cwait"></a>_cwait
Attend la fin d'un autre processus.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
intptr_t _cwait(   
   int *termstat,  
   intptr_t procHandle,  
   int action   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `termstat`  
 Pointeur vers une mémoire tampon où le code de résultat du processus spécifié sera stocké, ou NULL.  
  
 `procHandle`  
 Handle vers le processus à attendre (autrement dit, le processus qui doit se terminer avant le retour possible de `_cwait`).  
  
 `action`  
 NULL : valeur ignorée par les applications du système d'exploitation Windows ; pour d'autres applications : code d'action à effectuer sur `procHandle`.  
  
## <a name="return-value"></a>Valeur de retour  
 Quand le processus spécifié s'est correctement terminé, retourne le handle du processus spécifié et affecte à `termstat` le code de résultat retourné par le processus spécifié. Sinon, retourne -1 et définit `errno` comme suit.  
  
|Valeur|Description|  
|-----------|-----------------|  
|`ECHILD`|Aucun processus spécifié n’existe, `procHandle` n’est pas valide ou l’appel à l’API [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) ou [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) a échoué.|  
|`EINVAL`|`action` n'est pas valide.|  
  
 Pour plus d’informations sur ces codes de retour et d’autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_cwait` attend la fin de l'ID du processus spécifié fourni par `procHandle`. La valeur de `procHandle` passée à `_cwait` doit être la valeur retournée par l’appel à la fonction [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) qui a créé le processus spécifié. Si l'ID de processus se termine avant l'appel à `_cwait`, `_cwait` est immédiatement retourné. `_cwait` peut être utilisé par n'importe quel processus pour attendre tout autre processus connu pour lequel il existe un handle valide (`procHandle`).  
  
 `termstat` pointe vers une mémoire tampon où le code de retour du processus spécifié sera stocké. La valeur de `termstat` indique si le processus spécifié s’est correctement terminé en appelant l’API Windows [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx). `ExitProcess` est appelé en interne si le processus spécifié appelle `exit` ou `_exit`, est retourné à partir de `main` ou atteint la fin de `main`. Pour plus d’informations sur la valeur qui est passée par le biais de `termstat`, consultez [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx). Si `_cwait` est appelé à l'aide d'une valeur NULL pour `termstat`, le code de retour du processus spécifié n'est pas stocké.  
  
 Le paramètre `action` est ignoré par le système d'exploitation Windows car les relations parent-enfant ne sont pas implémentées dans ces environnements.  
  
 Sauf si `procHandle` est égal à -1 ou -2 (handles vers le thread ou processus actuel), le handle est fermé. Ainsi, dans ce cas, n'utilisez pas le handle retourné.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_cwait`|\<process.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
  
#define _CRT_RAND_S  
  
#include <windows.h>  
#include <process.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
// Macro to get a random integer within a specified range  
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))  
  
struct PROCESS  
{  
   int     nPid;  
   char    name[40];  
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };  
  
int main( int argc, char *argv[] )  
{  
   int termstat, c;  
   unsigned int number;  
  
   srand( (unsigned)time( NULL ) );    // Seed randomizer  
  
   // If no arguments, this is the calling process  
   if ( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for ( c = 0; c < 4; c++ ) {  
         _flushall();  
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],   
                                    process[c].name, NULL );  
      }  
  
      // Wait for randomly specified process, and respond when done   
      c = getrandom( 0, 3 );  
      printf( "Come here, %s.\n", process[c].name );  
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );  
      printf( "Thank you, %s.\n", process[c].name );  
  
   }  
   // If there are arguments, this must be a spawned process   
   else  
   {  
      // Delay for a period that's determined by process number  
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );  
      printf( "Hi, Dad. It's %s.\n", argv[1] );  
   }  
}  
```  
  
```Output  
Hi, Dad. It's Ann.  
Come here, Ann.  
Thank you, Ann.  
Hi, Dad. It's Beth.  
Hi, Dad. It's Carl.  
Hi, Dad. It's Dave.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)
