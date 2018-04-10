---
title: Spécification d’un fichier Inline | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef2183390b2aca2fb54e1468bd59e697374a355a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-an-inline-file"></a>Spécification d'un fichier inline
Spécifier deux crochets pointus (<<) dans la commande où *nom de fichier* doit apparaître. Les chevrons ne peut pas être une expansion macro.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<<[filename]  
```  
  
## <a name="remarks"></a>Notes  
 Lorsque la commande est exécutée, les chevrons sont remplacés par *nom de fichier*, si spécifié, ou par un nom unique généré par NMAKE. Si spécifié, *nom de fichier* doit suivre les chevrons sans espace ni tabulation. Un chemin d’accès est autorisé. Aucune extension n’est nécessaire ou pris par défaut. Si *nom de fichier* est spécifié, le fichier est créé en cours ou le répertoire spécifié, remplaçant les fichiers de ce nom ; sinon, il est créé dans le répertoire TMP (ou le répertoire actif, si la variable d’environnement TMP est non défini). Si une précédente *nom de fichier* est réutilisé, NMAKE remplace le fichier précédent.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)