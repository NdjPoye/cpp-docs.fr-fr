---
title: "_execlpe, _wexeclpe | Microsoft Docs"
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
  - "_execlpe"
  - "_wexeclpe"
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
  - "_wexeclpe"
  - "execlpe"
  - "wexeclpe"
  - "_execlpe"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_execlpe (fonction)"
  - "_wexeclpe (fonction)"
  - "execlpe (fonction)"
  - "wexeclpe (fonction)"
ms.assetid: 07b861da-3e7e-4f1d-bb80-ad69b55e5162
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _execlpe, _wexeclpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Charge et exécute les nouveaux processus enfant.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
intptr_t _execlpe(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexeclpe(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### Paramètres  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `arg0`, `...``argn`  
 Liste de pointeurs vers les paramètres.  
  
 `envp`  
 Tableau de pointeurs vers les paramètres d'environnement.  
  
## Valeur de retour  
 En cas de réussite, ces fonctions ne retournent pas au processus appelant.  Une valeur de retour égale à 1 indique une erreur, auquel cas la variable globale `errno` est définie.  
  
|Valeur de `errno`|Description|  
|-----------------------|-----------------|  
|`E2BIG`|L'espace requis pour les arguments et les paramètres d'environnement dépasse 32 Ko.|  
|`EACCES`|Le fichier spécifié possède un verrou ou une violation de partage.|  
|`EINVAL`|Paramètre non valide.|  
|`EMFILE`|Trop de fichiers ouverts \(le fichier spécifié doit être ouvert pour déterminer s'il est exécutable\).|  
|`ENOENT`|Fichier ou chemin d'accès introuvable.|  
|`ENOEXEC`|Le fichier spécifié n'est pas exécutable ou a un format de fichier exécutable non valide.|  
|`ENOMEM`|Mémoire insuffisante pour exécuter le nouveau processus ; la mémoire disponible est endommagée ; ou il existe un bloc non valide, indiquant que le processus appelant n'a pas été alloué correctement.|  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chacune de ces fonctions charge et exécute un nouveau processus, en passant chaque argument de ligne de commande comme paramètre distinct et en passant également un tableau de pointeurs vers des paramètres d'environnement.  Ces fonctions utilisent la variable d'environnement `PATH` pour rechercher le fichier à exécuter.  
  
 Les fonctions `_execlpe` valident leurs paramètres.  Si soit `cmdname` ou `arg0` est un pointeur null ou une chaîne de caractères vide, ces fonctions appellent le gestionnaire de paramètre non valide, décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1.  Aucun nouveau processus lancé.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`_execlpe`|\<process.h\>|\<errno.h\>|  
|`_wexeclpe`|\<process.h\> ou \<wchar.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [Fonctions \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md).  
  
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