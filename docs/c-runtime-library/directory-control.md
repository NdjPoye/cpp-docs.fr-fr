---
title: "Contrôle de répertoire | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 49084f97470965f2b3d8fec627f0d0c92f4ec522
ms.lasthandoff: 02/24/2017

---
# <a name="directory-control"></a>Contrôle de répertoire
Ces routines accèdent à des informations, les modifient et obtiennent des informations sur la structure de répertoires.  
  
### <a name="directory-control-routines"></a>Routines de contrôle de répertoire  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|---------|-------------------------------|  
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Modifier le répertoire de travail actuel|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Modifier le lecteur actuel|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Obtenir le répertoire de travail actuel pour le lecteur par défaut|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Obtenir le répertoire de travail actuel pour le lecteur spécifié|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Remplit une structure `_diskfree_t` avec des informations relatives à un lecteur de disque.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Obtenir le lecteur actuel (par défaut)|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Retourne un masque de bits qui représente les lecteurs de disque actuellement disponibles.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Créer un répertoire|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx), [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Supprimer un répertoire|[System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Rechercher un fichier donné dans les chemins spécifiés|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Gestion de fichiers](../c-runtime-library/file-handling.md)   
 [Appels système](../c-runtime-library/system-calls.md)
