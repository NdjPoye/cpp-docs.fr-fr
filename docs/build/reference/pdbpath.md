---
title: -PDBPATH | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /pdbpath
dev_langs: C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ccbcedbf9cdd376fa7d9bced5c9d49542cee9f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pdbpath"></a>/PDBPATH
```  
/PDBPATH[:VERBOSE] filename  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 *filename*  
 Le nom du fichier .dll ou .exe pour lequel vous souhaitez trouver le fichier .pdb correspondant.  
  
 COMMENTAIRES (facultatif)  
 Signale tous les répertoires où une tentative a été effectuée pour localiser le fichier .pdb.  
  
## <a name="remarks"></a>Notes  
 /PDBPATH l’ordinateur en suivant les mêmes chemins que le débogueur pour recherche un fichier .pdb et signalera qui, le cas échéant, les fichiers .pdb correspondant dans le fichier spécifié dans *nom de fichier*.  
  
 Lorsque vous utilisez le débogueur Visual Studio, vous pouvez rencontrer un problème dû au fait que le débogueur utilise un fichier .pdb pour une autre version du fichier que vous déboguez.  
  
 /PDBPATH les fichiers .pdb avec les chemins d’accès suivants :  
  
-   Vérifiez l’emplacement où se trouve le fichier exécutable.  
  
-   Vérifiez l’emplacement du PDB écrit dans le fichier exécutable. Il s’agit généralement l’emplacement au moment où que l’image a été liée.  
  
-   Vérifiez le long du chemin de recherche configuré dans l’IDE de Visual Studio.  
  
-   Vérifiez les chemins dans _NT_SYMBOL_PATH et _NT_ALT_SYMBOL_PATH variables d’environnement.  
  
-   Vérifiez dans le répertoire Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)   
 [/PDBALTPATH (utiliser un chemin autre PDB)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)