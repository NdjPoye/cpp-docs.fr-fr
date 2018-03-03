---
title: -IMPORTS (DUMPBIN) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1866c8d522e7482781aa65e58d93ccb09e6b265f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)
```  
/IMPORTS[:file]  
```  
  
 Cette option affiche la liste des DLL (à lien statique et [chargé différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)) qui sont importées vers un fichier exécutable ou une DLL et toutes les importations individuelles à partir de chacune de ces DLL.  
  
 Le paramètre facultatif `file` spécification vous permet de spécifier que les importations de DLL uniquement seront affichera. Exemple :  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## <a name="remarks"></a>Notes  
 La sortie affichée par cette option est similaire à la [/EXPORTE](../../build/reference/dash-exports.md) sortie.  
  
 Uniquement les [/HEADERS](../../build/reference/headers.md) (option DUMPBIN) est disponible pour les fichiers générés par le [/GL](../../build/reference/gl-whole-program-optimization.md) option du compilateur.  
  
## <a name="see-also"></a>Voir aussi  
 [DUMPBIN, options](../../build/reference/dumpbin-options.md)