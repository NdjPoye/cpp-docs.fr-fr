---
title: "_rmdir, _wrmdir | Microsoft Docs"
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
  - "_wrmdir"
  - "_rmdir"
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
  - "trmdir"
  - "_trmdir"
  - "wrmdir"
  - "_rmdir"
  - "_wrmdir"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rmdir (fonction)"
  - "_trmdir (fonction)"
  - "_wrmdir (fonction)"
  - "répertoires (C++), supprimer"
  - "répertoires (C++), supprimer"
  - "rmdir (fonction)"
  - "trmdir (fonction)"
  - "wrmdir (fonction)"
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rmdir, _wrmdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprime un répertoire.  
  
## Syntaxe  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### Paramètres  
 `dirname`  
 Chemin d'accès au répertoire à enlever.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne 0 si le répertoire a été supprimé avec succès.  Une valeur de retour de –1 indique une erreur et `errno` est fixé à une des valeurs suivantes:  
  
 **ENOTEMPTY**  
 Le chemin d'accès n'est pas un répertoire, le répertoire n'est pas vide, ou le répertoire est le répertoire de travail actuel ou le répertoire racine.  
  
 `ENOENT`  
 Le chemin d'accès n'est pas valide.  
  
 **EACCES**  
 Un programme gère ouvertement le répertoire.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_rmdir` supprime le répertoire spécifié par `dirname`.  Le répertoire doit être vide, et il ne doit pas être le répertoire de travail actuel ou le répertoire racine.  
  
 `_wrmdir` est une version à caractères larges de `_rmdir`; l'argument `dirname` vers `_wrmdir` est une chaîne à caractères larges.  `_wrmdir` et `_rmdir` se comportent sinon de manière identique.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_rmdir`|\<direct.h\>|  
|`_wrmdir`|\<direct.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Consultez l'exemple de [\_mkdir](../../c-runtime-library/reference/mkdir-wmkdir.md).  
  
## Équivalent .NET Framework  
 [System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)