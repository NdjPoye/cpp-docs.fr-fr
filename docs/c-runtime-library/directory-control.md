---
title: "Contrôle de répertoire | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.programs
dev_langs: C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 74d0bd9011c77d67383e36b15817a71f853a409b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="directory-control"></a>Contrôle de répertoire
Ces routines accèdent à des informations, les modifient et obtiennent des informations sur la structure de répertoires.  
  
### <a name="directory-control-routines"></a>Routines de contrôle de répertoire  
  
|Routine|Utilisation|  
|-------------|---------|  
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Modifier le répertoire de travail actuel|  
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Modifier le lecteur actuel|  
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Obtenir le répertoire de travail actuel pour le lecteur par défaut|  
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Obtenir le répertoire de travail actuel pour le lecteur spécifié|  
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Remplit une structure `_diskfree_t` avec des informations relatives à un lecteur de disque.|  
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Obtenir le lecteur actuel (par défaut)|  
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Retourne un masque de bits qui représente les lecteurs de disque actuellement disponibles.|  
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Créer un répertoire|  
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Supprimer un répertoire|  
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Rechercher un fichier donné dans les chemins spécifiés|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Gestion de fichiers](../c-runtime-library/file-handling.md)   
 [Appels système](../c-runtime-library/system-calls.md)