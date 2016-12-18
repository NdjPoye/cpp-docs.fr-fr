---
title: "Gestion de fichiers | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.files"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fichiers (C++), gérer"
  - "fichiers (C++), manipuler"
  - "fichiers (C++), ouvrir"
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Gestion de fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces routines vous permettent de créer, supprimer et manipuler des fichiers et de définir et vérifier les autorisations d'accès aux fichiers.  
  
 Les bibliothèques Runtime C limitent à 512 le nombre de fichiers pouvant être ouverts simultanément. Toute tentative visant à ouvrir plus de descripteurs de fichiers ou de flux de fichiers que le nombre maximal autorisé entraîne un échec du programme. Utilisez [\_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) pour modifier ce nombre.  
  
 Les routines suivantes fonctionnent sur les fichiers désignés par un descripteur de fichier.  
  
### Routines de gestion de fichiers \(descripteur de fichier\)  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|-----------------|-------------------------------|  
|[\_chsize](../c-runtime-library/reference/chsize.md),[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|Modifier la taille de fichier|[System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx), [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)|  
|[\_filelength, \_filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Obtenir la longueur de fichier|[System::IO::Stream::Length](https://msdn.microsoft.com/en-us/library/system.io.stream.length.aspx), [System::IO::FileStream::Length](https://msdn.microsoft.com/en-us/library/system.io.filestream.length.aspx)|  
|[\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Obtenir des informations d’état de fichier sur le descripteur|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Retourne le descripteur de fichier de système d’exploitation associé au descripteur de fichier Runtime C existant.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_isatty](../c-runtime-library/reference/isatty.md)|Rechercher un périphérique de caractères|[System::IO::Stream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.filestream.canwrite.aspx), [System::IO::FileStream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.stream.canwrite.aspx)|  
|[\_locking](../c-runtime-library/reference/locking.md)|Verrouiller des zones de fichier|[System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Associer un descripteur de fichier Runtime C à un descripteur de fichier de système d’exploitation existant|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_setmode](../c-runtime-library/reference/setmode.md)|Définir le mode de traduction de fichiers|[System::IO::BinaryReader Class](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx), [System::IO::TextReader Class](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)|  
  
 Les routines suivantes fonctionnent sur les fichiers spécifiés par un chemin d’accès ou un nom de fichier.  
  
### Routines de gestion de fichiers \(chemin d'accès ou nom de fichier\)  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|-----------------|-------------------------------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md), [\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|Vérifier le paramètre d’autorisation de fichier|[Énumération System::IO::FileAccess](https://msdn.microsoft.com/en-us/library/4z36sx0f.aspx)|  
|[\_chmod, \_wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Modifier le paramètre d’autorisation de fichier|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx), [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)|  
|[\_fullpath, \_wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Développer un chemin d’accès relatif vers son nom de chemin d’accès absolu|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Fusionner des composants de chemin d’accès en un seul chemin d’accès complet|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Créer un nom de fichier unique|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[remove, \_wremove](../c-runtime-library/reference/remove-wremove.md)|Supprimer le fichier|[System::IO::file::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
|[rename, \_wrename](../c-runtime-library/reference/rename-wrename.md)|Renommer un fichier|[System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)|  
|[\_splitpath, \_wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Analyser un chemin d’accès en composants|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_stat, \_stat64, \_stati64, \_wstat, \_wstat64, \_wstati64](../c-runtime-library/reference/stat-functions.md)|Obtenir des informations d’état de fichier sur un fichier nommé|[System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx), [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx), [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx), [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../c-runtime-library/reference/umask-s.md)|Définir le masque d’autorisation par défaut pour les nouveaux fichiers créés par programme|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)|  
|[\_unlink, \_wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Supprimer le fichier|[System::IO::file::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
  
 Les routines suivantes permettent d’ouvrir les fichiers.  
  
### Routines de gestion de fichiers \(ouvrir un fichier\)  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|-----------------|-------------------------------|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Ouvre un fichier et retourne un pointeur vers le fichier ouvert.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Ouvre un flux avec le partage de fichiers et retourne un pointeur vers le fichier ouvert.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|Ouvre un fichier et retourne un descripteur de fichier au fichier ouvert.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Ouvre un fichier avec le partage de fichiers et retourne un descripteur de fichier au fichier ouvert.||  
|[\_pipe](../c-runtime-library/reference/pipe.md)|Crée un canal pour la lecture et l’écriture.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Réaffecte un pointeur de fichier.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
  
 Les fonctions suivantes permettent de modifier la représentation du fichier entre une structure `FILE`, un descripteur de fichier et un descripteur de fichier Win32.  
  
||||  
|-|-|-|  
|[\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Associe un flux à un fichier ouvert précédemment pour une E\/S de bas niveau et retourne un pointeur vers le flux ouvert.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.filestream.aspx)|  
|[\_fileno](../c-runtime-library/reference/fileno.md)|Obtient le descripteur de fichier associé à un flux.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Retourne le descripteur de fichier de système d’exploitation associé au descripteur de fichier Runtime C existant.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Associe un descripteur de fichier Runtime C à un descripteur de fichier de système d’exploitation existant.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
  
 Les fonctions Win32 suivantes permettent aussi d’ouvrir des fichiers et des canaux :  
  
-   [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)  
  
-   [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)  
  
-   [CreateNamedPipe](http://msdn.microsoft.com/library/windows/desktop/aa365150.aspx)  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Contrôle de répertoire](../c-runtime-library/directory-control.md)   
 [Appels système](../c-runtime-library/system-calls.md)