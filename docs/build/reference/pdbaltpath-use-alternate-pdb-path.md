---
title: -/PDBALTPATH (utiliser un chemin autre PDB) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /pdbaltpath
dev_langs: C++
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9053bc206a465eb32d8007fb8d58d13d45eb4a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Utiliser un autre chemin d’accès PDB)
```  
/PDBALTPATH:pdb_file_name  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 *pdb_file_name*  
 Chemin d’accès et nom de fichier du fichier .pdb.  
  
## <a name="remarks"></a>Notes  
 Utilisez cette option pour fournir un autre emplacement pour le fichier de base de données de programme (.pdb) dans un fichier binaire compilé. Normalement, l'éditeur de liens enregistre l'emplacement du fichier .pdb dans les binaires qu'il produit. Vous pouvez utiliser cette option pour fournir un chemin d'accès et un nom de fichier différents pour le fichier .pdb. Les informations fournies avec /PDBALTPATH ne modifient pas l'emplacement ni le nom du fichier .pdb réel. Elles modifient les informations que l'éditeur de liens écrit dans le fichier binaire. Cela vous permet de fournir un chemin d'accès indépendant de la structure de fichiers de l'ordinateur de build. Cette option a deux applications courantes : fournir un chemin d’accès réseau et fournir un fichier sans informations de chemin d’accès.  
  
 La valeur de *pdb_file_name* peut être une chaîne arbitraire, une variable d’environnement ou **% _PDB %**. L’éditeur de liens développera une variable d’environnement, telle que **%SystemRoot%**, sa valeur. L’éditeur de liens définit les variables d’environnement **% _PDB %** et **_EXT %**. **% _PDB %** se développe vers le nom de fichier du fichier .pdb réel sans aucune information de chemin d’accès et **_EXT %** est l’extension de fichier exécutable généré.  
  
## <a name="see-also"></a>Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)   
 [/PDBPATH](../../build/reference/pdbpath.md)