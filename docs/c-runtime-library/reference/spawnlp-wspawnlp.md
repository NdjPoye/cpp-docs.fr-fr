---
title: _spawnlp, _wspawnlp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wspawnlp
- _spawnlp
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
- _wspawnlp
- wspawnlp
- _spawnlp
dev_langs: C++
helpviewer_keywords:
- wspawnlp function
- _spawnlp function
- processes, creating
- processes, executing new
- _wspawnlp function
- process creation
- spawnlp function
ms.assetid: 74fc6e7a-4f24-4103-9387-7177875875e6
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0453ce194e9321393f87ed492b92cf3ae11d4bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="spawnlp-wspawnlp"></a>_spawnlp, _wspawnlp
Crée et exécute un nouveau processus.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
intptr_t _spawnlp(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wspawnlp(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `mode`  
 Mode d'exécution du processus appelant.  
  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `arg0, arg1, ... argn`  
 Liste des pointeurs vers les arguments. L’argument `arg0` est généralement un pointeur vers `cmdname`. Les arguments `arg1` à `argn` sont des pointeurs vers les chaînes de caractères formant la nouvelle liste d’arguments. Après `argn`, il doit exister un pointeur `NULL` pour marquer la fin de la liste des arguments.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de retour d'une routine `_spawnlp` ou `_wspawnlp` synchrone (`_P_WAIT` spécifié pour `mode`) est l'état de sortie du nouveau processus. La valeur de retour d'une routine `_spawnlp` ou `_wspawnlp` asynchrone (`_P_NOWAIT` ou `_P_NOWAITO` spécifié pour `mode`) est le handle du processus. L'état de sortie est 0 si le processus s'est terminé normalement. Vous pouvez définir l'état de sortie à une valeur différente de zéro si le processus engendré appelle spécifiquement la routine `exit` avec un argument différent de zéro. Si le nouveau processus ne définissait pas explicitement un état de sortie positif, un état de sortie positif indique une sortie anormale avec arrêt ou interruption. Une valeur de retour de -1 indique une erreur (le nouveau processus n’est pas lancé). Dans ce cas, `errno` a l'une des valeurs suivantes.  
  
 `E2BIG`  
 La liste des arguments dépasse 1024 octets.  
  
 `EINVAL`  
 Argument `mode` non valide.  
  
 `ENOENT`  
 Fichier ou chemin d'accès introuvable.  
  
 `ENOEXEC`  
 Le fichier spécifié n'est pas exécutable ou a un format de fichier exécutable non valide.  
  
 `ENOMEM`  
 Mémoire insuffisante pour exécuter le nouveau processus.  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions crée et exécute un nouveau processus, passant chaque argument de ligne de commande en tant que paramètre distinct et utilisant la variable d’environnement `PATH` pour rechercher le fichier à exécuter.  
  
 Ces fonctions valident leurs paramètres. Si `cmdname` ou `arg0` est une chaîne vide ou un pointeur null, ces fonctions génèrent une exception de paramètre non valide, comme décrit dans [Parameter Validation](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL`et retournent -1. Aucun nouveau processus généré.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_spawnlp`|\<process.h>|  
|`_wspawnlp`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l'exemple de [Fonctions _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)