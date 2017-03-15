---
title: "_execl, _wexecl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execl"
  - "_wexecl"
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
  - "_execl"
  - "_wexecl"
  - "wexecl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_execl (fonction)"
  - "_wexecl (fonction)"
  - "execl (fonction)"
  - "wexecl (fonction)"
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _execl, _wexecl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Charge et exécute les nouveaux processus enfant.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### Paramètres  
 `cmdname`  
 Chemin d'accès du fichier à exécuter.  
  
 `arg0`, `...``argn`  
 Liste de pointeurs vers les paramètres.  
  
## Valeur de retour  
 En cas de réussite, ces fonctions ne retournent pas au processus appelant.  Une valeur de retour égale à 1 indique une erreur, auquel cas la variable globale `errno` est définie.  
  
|valeur errno|Description|  
|------------------|-----------------|  
|`E2BIG`|L'espace requis pour les arguments et les paramètres d'environnement dépasse 32 Ko.|  
|`EACCES`|Le fichier spécifié possède un verrou ou une violation de partage.|  
|`EINVAL`|Paramètre non valide \(un ou plusieurs paramètres est un pointeur null ou une chaîne vide\).|  
|`EMFILE`|Trop de fichiers ouverts \(le fichier spécifié doit être ouvert pour déterminer s'il est exécutable\).|  
|`ENOENT`|Le fichier ou chemin d'accès est introuvable.|  
|`ENOEXEC`|Le fichier spécifié n'est pas exécutable ou a un format de fichier exécutable non valide.|  
|`ENOMEM`|Mémoire insuffisante pour exécuter le nouveau processus ; la mémoire disponible est endommagée ; ou il existe un bloc non valide, indiquant que le processus appelant n'a pas été alloué correctement.|  
  
## Notes  
 Chacune de ces fonctions charge et exécute un nouveau processus, en passant chaque argument de ligne de commande comme paramètre séparé.  Le premier argument est le nom du fichier de commandes ou de fichier exécutable, et le deuxième argument doit être identique au premier.  Elle devient `argv[0]` dans le processus exécuté.  Le troisième argument est le premier argument, `argv[1]`, du processus en cours d'exécution.  
  
 Ces fonctions `_execl` valident leurs paramètres.  Si `cmdname` ou `arg0` est un pointeur null ou une chaîne vide, ces fonctions appellent le gestionnaire de paramètre non valide comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à `EINVAL` et retournent \-1.  Aucun nouveau processus n'est généré.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`_execl`|\<process.h\>|\<errno.h\>|  
|`_wexecl`|\<process.h\> or \<wchar.h\>|\<errno.h\>|  
  
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