---
title: "_getdcwd_nolock, _wgetdcwd_nolock | Microsoft Docs"
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
  - "_wgetdcwd_nolock"
  - "_getdcwd_nolock"
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
apitype: "DLLExport"
f1_keywords: 
  - "_wgetdcwd_nolock"
  - "tgetdcwd_nolock"
  - "wgetdcwd_nolock"
  - "_getdcwd_nolock"
  - "_tgetdcwd_nolock"
  - "getdcwd_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getdcwd_nolock (fonction)"
  - "_tgetdcwd_nolock (fonction)"
  - "_wgetdcwd_nolock (fonction)"
  - "répertoire de travail en cours"
  - "répertoires (C++), de travail en cours"
  - "getdcwd_nolock (fonction)"
  - "tgetdcwd_nolock (fonction)"
  - "wgetdcwd_nolock (fonction)"
  - "répertoire de travail"
ms.assetid: d9bdf712-43f8-4173-8f9a-844e82beaa97
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getdcwd_nolock, _wgetdcwd_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient le chemin complet du répertoire de travail actuel sur le lecteur spécifié.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *_getdcwd_nolock(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd_nolock(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### Paramètres  
 `drive`  
 Lecteurs de disques  
  
 `buffer`  
 Emplacement de stockage pour le tracé.  
  
 `maxlen`  
 La longueur maximale du tracé en caractères est : `char` pour `_getdcwd` et `wchar_t` pour `_wgetdcwd`.  
  
## Valeur de retour  
 Consultez [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md).  
  
## Notes  
 `_getdcwd_nolock` et `_wgetdcwd_nolock` sont identiques à `_getdcwd` et `_wgetdcwd`, respectivement, sauf qu'ils ne sont pas protégés des interférences avec d'autres threads.  Elles peuvent être plus rapides, car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tgetdcwd_nolock`|`_getdcwd_nolock`|`_getdcwd_nolock`|`_wgetdcwd_nolock`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getdcwd_nolock`|\<direct.h\>|  
|`_wgetdcwd_nolock`|\<direct.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)