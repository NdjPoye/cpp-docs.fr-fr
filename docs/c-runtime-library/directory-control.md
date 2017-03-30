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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 00a892376691f0d73b6ce0483cccf8bb063c43b4
ms.lasthandoff: 03/29/2017

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
