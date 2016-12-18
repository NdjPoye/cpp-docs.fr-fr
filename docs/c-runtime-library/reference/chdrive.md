---
title: "_chdrive | Microsoft Docs"
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
  - "_chdrive"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "chdrive"
  - "_chdrive"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chdrive (fonction)"
  - "chdrive (fonction)"
  - "lecteurs, modifier"
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chdrive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie le lecteur actif.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### Paramètres  
 `drive`  
 Un entier compris entre 1 et 26 qui spécifie le lecteur de travail actif \(1\=A, 2\=B, etc.\).  
  
## Valeur de retour  
 Zéro \(0\) si le lecteur de travail actuel a été modifié avec succès ; sinon, \-1.  
  
## Notes  
 Si `drive` n'est pas dans la plage de 1 à 26, le gestionnaire de paramètre non valide est appelé comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction **\_chdrive** retourne \-1, `errno` est défini à `EACCES` et `_doserrno` est défini à `ERROR_INVALID_DRIVE`.  
  
 La fonction **\_chdrive** n'est pas thread\-safe car elle dépend de la fonction **SetCurrentDirectory**, qui est elle\-même non thread\-safe.  Pour utiliser **\_chdrive** sans risque dans une application multithread, vous devez fournir votre propre synchronisation de threads.  Pour plus d'informations, accédez à [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542) puis recherchez **SetCurrentDirectory**.  
  
 Les modifications de fonction **\_chdrive** modifient uniquement le lecteur de travail actuel; **\_chdir** modifie le répertoire de travail actuel.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**\_chdrive**|\<direct.h\>|  
  
 Pour plus d'informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple pour [\_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## Équivalent .NET Framework  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)