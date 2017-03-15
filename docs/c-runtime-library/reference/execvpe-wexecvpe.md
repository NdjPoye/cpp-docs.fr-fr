---
title: "_execvpe, _wexecvpe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execvpe"
  - "_wexecvpe"
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
  - "wexecvpe"
  - "execvpe"
  - "_wexecvpe"
  - "_execvpe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_execvpe (fonction)"
  - "_wexecvpe (fonction)"
  - "execvpe (fonction)"
  - "wexecvpe (fonction)"
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _execvpe, _wexecvpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Charge et exécute les nouveaux processus enfant.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
intptr_t _execvpe(   
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wexecvpe(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### Paramètres  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `argv`  
 Tableau de pointeurs vers les paramètres.  
  
 `envp`  
 Tableau de pointeurs vers les paramètres d'environnement.  
  
## Valeur de retour  
 En cas de réussite, ces fonctions ne retournent pas au processus appelant.  Une valeur de retour égale à 1 indique une erreur, auquel cas la variable globale `errno` est définie.  
  
|Valeur `errno`|Description|  
|--------------------|-----------------|  
|`E2BIG`|L'espace nécessaire aux arguments et aux paramètres d'environnement dépasse 32 Ko.|  
|`EACCES`|Le fichier spécifié possède un verrou ou une violation de partage.|  
|`EMFILE`|Trop de fichiers sont ouverts.  \(Le fichier spécifié doit être ouvert pour déterminer s'il est exécutable.\)|  
|`ENOENT`|Fichier ou chemin d'accès introuvable.|  
|`ENOEXEC`|Le fichier spécifié n'est pas exécutable ou a un format de fichier exécutable non valide.|  
|`ENOMEM`|Mémoire insuffisante pour exécuter le nouveau processus ; la mémoire disponible est endommagée ; ou il existe un bloc non valide, ce qui indique que le processus appelant n'a pas été alloué correctement.|  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chacune de ces fonctions charge et exécute un nouveau processus, passe un tableau de pointeurs à des arguments de ligne de commande et un tableau de pointeurs aux paramètres d'environnement.  Ces fonctions utilisent la variable d'environnement `PATH` pour rechercher le fichier à exécuter.  
  
 Les fonctions `_execvpe` valident leurs paramètres.  Si `cmdname` est un pointeur null ou si `argv` est un pointeur null, un pointeur désignant un tableau vide ou un pointeur désignant un tableau dont le premier argument est une chaîne vide, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1.  Aucun processus lancé.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`_execvpe`|\<process.h\>|\<errno.h\>|  
|`_wexecvpe`|\<process.h\> ou \<wchar.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md).  
  
## Équivalent .NET Framework  
  
-   [Classe System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [Classe System::Diagnostics::ProcessStartInfo](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)