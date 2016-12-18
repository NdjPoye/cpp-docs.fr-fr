---
title: "Contr&#244;le de r&#233;pertoire | Microsoft Docs"
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
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "contrôles (C++), répertoire"
  - "routines de contrôle de répertoire"
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Contr&#244;le de r&#233;pertoire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces routines accèdent, modifient, et obtiennent des informations sur la structure du répertoire.  
  
### Routines de contrôle de répertoire  
  
|Routine|Utilisez|Équivalent de .NET Framework|  
|-------------|--------------|----------------------------------|  
|[\_chdir, \_wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Modifie le répertoire de travail en cours|[\<caps:sentence id\="tgt8" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_chdrive](../c-runtime-library/reference/chdrive.md)|Change le lecteur actuel|[\<caps:sentence id\="tgt11" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getcwd, \_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Obtient le répertoire de travail actuel pour le lecteur par défaut|[\<caps:sentence id\="tgt14" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdcwd, \_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Obtient le répertoire de travail actuel pour le lecteur spécifié|[\<caps:sentence id\="tgt16" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Remplit une structure `_diskfree_t` avec des informations sur un lecteur de disque.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_getdrive](../c-runtime-library/reference/getdrive.md)|Obtient le lecteur actuel \(par défaut\)|[\<caps:sentence id\="tgt23" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdrives](../c-runtime-library/reference/getdrives.md)|Retourne un masque binaire qui représente les lecteurs de disques actuellement disponibles.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_mkdir, \_wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Faites un nouveau répertoire|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx), [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[\_rmdir, \_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Supprimer un répertoire|[\<caps:sentence id\="tgt32" sentenceid\="de5c5e84e86fdd3cd99296d3b2518f57" class\="tgtSentence"\>System::IO::Directory::Delete\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [\_searchenv\_s, \_wsearchenv\_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Recherchez le fichier spécifique sur les chemins d'accès spécifiés|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Gestion de fichiers](../c-runtime-library/file-handling.md)   
 [Appels système](../c-runtime-library/system-calls.md)