---
title: "_spawnvp, _wspawnvp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wspawnvp"
  - "_spawnvp"
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
  - "_wspawnvp"
  - "_spawnvp"
  - "wspawnvp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wspawnvp (fonction)"
  - "processus, création"
  - "_wspawnvp (fonction)"
  - "processus, exécuter un nouveau"
  - "spawnvp (fonction)"
  - "processus, création"
  - "_spawnvp (fonction)"
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _spawnvp, _wspawnvp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un processus et l'exécute.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
intptr_t _spawnvp(  
   int mode,  
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wspawnvp(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### Paramètres  
 `mode`  
 Mode d'exécution de l'appel du processus.  
  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `argv`  
 Tableau de pointeurs vers les arguments. L'argument `argv`\[0\] est généralement un pointeur qui désigne un chemin d'accès en mode réel ou un nom de programme en mode protégé, tandis que `argv`\[1\] à `argv`\[`n`\] sont des pointeurs qui pointent vers les chaînes de caractères qui forment la nouvelle liste d'arguments. L'argument `argv`\[`n` \+1\] doit être un pointeur `NULL` pour marquer la fin de la liste d'arguments.  
  
## Valeur de retour  
 La valeur de retour d'une routine `_spawnvp` ou `_wspawnvp` synchrone \(`_P_WAIT` spécifiée pour `mode`\) est l'état de sortie du nouveau processus. La valeur de retour d'une routine `_spawnvp` ou `_wspawnvp` asynchrone \(`_P_NOWAIT` ou `_P_NOWAITO` spécifié pour `mode`\) est le handle du processus. L'état de sortie est 0 si le processus s'est terminé normalement. Vous pouvez attribuer à l'état de sortie une valeur différente de zéro si le processus engendré utilise spécifiquement un argument différent de zéro pour appeler la routine `exit`. Si le nouveau processus ne définissait pas explicitement un état de sortie positif, un état de sortie positif indique une sortie anormale avec arrêt ou interruption. Une valeur de retour égale à 1 indique une erreur \(le nouveau processus n'est pas lancé\). Dans ce cas, `errno` a l'une des valeurs suivantes :  
  
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
  
 Pour plus d’informations sur ces codes de retour et d’autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Après avoir créé et exécuté un processus, chacune de ces fonctions passe un tableau de pointeurs à des arguments de ligne de commande et utilise la variable d'environnement `PATH` pour rechercher le fichier à exécuter.  
  
 Ces fonctions valident leurs paramètres. Si `cmdname` ou `argv` est un pointeur null ou si `argv` pointe vers un pointeur null ou encore que `argv[0]` est une chaîne vide, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1. Aucun nouveau processus généré.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_spawnvp`|\<stdio.h\> ou \<process.h\>|  
|`_wspawnvp`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l’exemple dans [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md).  
  
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