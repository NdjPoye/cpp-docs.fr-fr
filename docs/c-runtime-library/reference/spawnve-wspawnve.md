---
title: "_spawnve, _wspawnve | Microsoft Docs"
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
  - "_spawnve"
  - "_wspawnve"
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
  - "wspawnve"
  - "_spawnve"
  - "_wspawnve"
  - "spawnve"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_spawnve (fonction)"
  - "_wspawnve (fonction)"
  - "création de processus"
  - "processus, créer"
  - "processus, exécuter un nouveau"
  - "spawnve (fonction)"
  - "wspawnve (fonction)"
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _spawnve, _wspawnve
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée et exécute un nouveau processus.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
intptr_t _spawnve(  
   int mode,  
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wspawnve(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### Paramètres  
 `mode`  
 Mode d'exécution d'un processus appelant.  
  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `argv`  
 Tableau de pointeurs vers les arguments.  L'argument `argv`\[0\] est généralement un pointeur vers un chemin d'accès en mode réel ou le nom du programme en mode protégé, et `argv`\[1\] à `argv`\[`n`\] sont des pointeurs vers les chaînes de caractères qui forment la nouvelle liste d'arguments.  L'argument `argv`\[`n` \+1\] doit être un pointeur `NULL` pour marquer la fin de la liste d'arguments.  
  
 `envp`  
 Tableau de pointeurs vers les paramètres d'environnement.  
  
## Valeur de retour  
 La valeur de retour de `_spawnve` synchrones ou d'`_wspawnve` \(`_P_WAIT` spécifié pour `mode`\) est l'état de sortie du nouveau processus.  La valeur de retour d'un `_spawnve` asynchrone ou de `_wspawnve` \(`_P_NOWAIT` ou `_P_NOWAITO` spécifié pour `mode`\) est le handle de processus.  L'état de sortie est 0 si le processus s'est terminé normalement.  Vous pouvez définir l'état de sortie à une valeur différente de zéro si le processus engendré appelle spécifiquement la routine `exit` avec un argument différent de zéro.  Si le nouveau processus ne définissait pas explicitement un état de sortie positif, un état de sortie positif indique une sortie anormale avec arrêt ou interruption.  Une valeur de retour égale à 1 indique une erreur \(le nouveau processus n'est pas lancé\).  Dans ce cas, `errno` a l'une des valeurs suivantes.  
  
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
 Chacune de ces fonctions crée et exécute un nouveau processus, en passant un tableau de pointeurs vers des arguments de ligne de commande et un tableau de pointeurs vers les paramètres d'environnement.  
  
 Ces fonctions valident leurs paramètres.  Si `cmdname` ou `argv` est un pointeur null, ou si `argv` pointe vers le pointeur null, ou `argv[0]` est une chaîne vide, le gestionnaire de paramètre invalide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1.  Aucun nouveau processus généré.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_spawnve`|\<stdio.h\> ou \<process.h\>|  
|`_wspawnve`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
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