---
title: _spawnlpe, _wspawnlpe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _spawnlpe
- _wspawnlpe
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
- spawnlpe
- _wspawnlpe
- _spawnlpe
- wspawnlpe
dev_langs:
- C++
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
caps.latest.revision: 18
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
ms.openlocfilehash: 9831f7056ef91f64bba54740fbf7a372beb8f335
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="spawnlpe-wspawnlpe"></a>_spawnlpe, _wspawnlpe
Crée et exécute un nouveau processus.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
intptr_t _spawnlpe(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnlpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `mode`  
 Mode d'exécution du processus appelant.  
  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `arg0, arg1, ... argn`  
 Liste des pointeurs vers les arguments. L'argument `arg0` est généralement un pointeur vers `cmdname`. Les arguments `arg1` à `argn` sont des pointeurs vers les chaînes de caractères qui forment la nouvelle liste d'arguments. Après `argn`, il doit exister un pointeur `NULL` pour marquer la fin de la liste des arguments.  
  
 `envp`  
 Tableau de pointeurs vers les paramètres d'environnement.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de retour d'une routine `_spawnlpe` ou `_wspawnlpe` synchrone (`_P_WAIT` spécifié pour `mode`) est l'état de sortie du nouveau processus. La valeur de retour d'une routine `_spawnlpe` ou `_wspawnlpe` asynchrone (`_P_NOWAIT` ou `_P_NOWAITO` spécifié pour `mode`) est le handle du processus. L'état de sortie est 0 si le processus s'est terminé normalement. Vous pouvez attribuer à l'état de sortie une valeur différente de zéro si le processus engendré utilise spécifiquement un argument différent de zéro pour appeler la routine `exit`. Si le nouveau processus ne définissait pas explicitement un état de sortie positif, un état de sortie positif indique une sortie anormale provoquée par un abandon ou une interruption. Une valeur de retour de -1 indique une erreur (le nouveau processus n’est pas lancé). Dans ce cas, `errno` a l'une des valeurs suivantes.  
  
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
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions crée et exécute un nouveau processus, passe chaque argument de ligne de commande en tant que paramètre distinct et passe un tableau de pointeurs aux paramètres d’environnement. Ces fonctions utilisent la variable d'environnement `PATH` pour rechercher le fichier à exécuter.  
  
 Ces fonctions valident leurs paramètres. Si `cmdname` ou `arg0` est une chaîne vide ou un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Parameter Validation](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL`et retournent -1. Aucun nouveau processus généré.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_spawnlpe`|\<process.h>|  
|`_wspawnlpe`|\<stdio.h> ou \<wchar.h>|  
  
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
