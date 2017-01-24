---
title: "_spawnle, _wspawnle | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_spawnle"
  - "_wspawnle"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "spawnle"
  - "_spawnle"
  - "wspawnle"
  - "_wspawnle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "spawnle (fonction)"
  - "processus, création"
  - "_wspawnle (fonction)"
  - "processus, exécuter un nouveau"
  - "processus, création"
  - "wspawnle (fonction)"
  - "_spawnle (fonction)"
ms.assetid: 80308892-2815-49b1-8cca-53894c366f5a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _spawnle, _wspawnle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée et exécute un nouveau processus.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
intptr_t _spawnle(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnle(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### Paramètres  
 `mode`  
 Mode d'exécution du processus appelant.  
  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `arg0, arg1, ... argn`  
 Liste des pointeurs vers les arguments. L’argument `arg0` est généralement un pointeur vers `cmdname`. Les arguments `arg1` à `argn` sont des pointeurs vers les chaînes de caractères formant la nouvelle liste d’arguments. Après `argn`, il doit exister un pointeur `NULL` pour marquer la fin de la liste des arguments.  
  
 `envp`  
 Tableau de pointeurs vers les paramètres d'environnement.  
  
## Valeur de retour  
 La valeur de retour d’une routine `_spawnle` ou `_wspawnle` synchrone \(\_`P_WAIT` spécifié pour `mode`\) est l’état de sortie du nouveau processus. La valeur de retour d'une routine `_spawnle` ou `_wspawnle` asynchrone \(`_P_NOWAIT` ou `_P_NOWAITO` spécifié pour `mode`\) est le handle du processus. L'état de sortie est 0 si le processus s'est terminé normalement. Vous pouvez définir l'état de sortie à une valeur différente de zéro si le processus engendré appelle spécifiquement la routine `exit` avec un argument différent de zéro. Si le nouveau processus ne définissait pas explicitement un état de sortie positif, un état de sortie positif indique une sortie anormale avec arrêt ou interruption. Une valeur de retour égale à 1 indique une erreur \(le nouveau processus n'est pas lancé\). Dans ce cas, `errno` a l'une des valeurs suivantes.  
  
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
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chacune de ces fonctions crée et exécute un nouveau processus, passant chaque argument de ligne de commande en tant que paramètre distinct et passant également un tableau de pointeurs aux paramètres d’environnement.  
  
 Ces fonctions valident leurs paramètres. Si `cmdname` ou `arg0` est une chaîne vide ou un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1. Aucun nouveau processus généré.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_spawnle`|\<process.h\>|  
|`_wspawnle`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [Fonctions \_spawn, \_wspawn](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## Équivalent .NET Framework  
  
-   [Classe System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [Classe System::Diagnostics::ProcessStartInfo](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)