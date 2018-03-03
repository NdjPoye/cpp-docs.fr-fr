---
title: "Définition de module (. Fichiers def) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49f5eb5b75bad22b59cb4fbb98554bbfd44d13b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="module-definition-def-files"></a>Fichiers de définition de module (.Def)
Les fichiers de définition de module (.def) fournissent à l’éditeur de liens avec des informations sur les exportations, attributs et d’autres informations sur le programme à lier. Un fichier .def est très utile lors de la création d’une DLL. Étant donné que [les options de l’éditeur de liens](../../build/reference/linker-options.md) qui peut être utilisé au lieu des instructions de définition de module, les fichiers .def ne sont généralement pas nécessaires. Vous pouvez également utiliser [__declspec (dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) comme un moyen de spécifier des fonctions exportées.  
  
 Vous pouvez appeler un fichier .def pendant la phase de l’éditeur de liens avec la [/DEF (spécifier un fichier de définition de Module)](../../build/reference/def-specify-module-definition-file.md) option de l’éditeur de liens.  
  
 Si vous générez un fichier .exe qui ne possède aucune exportation, à l’aide d’un fichier .def rend votre sortie plus lent et que le chargement du fichier.  
  
 Pour obtenir un exemple, consultez [exportation à partir d’une DLL à l’aide de fichiers DEF](../../build/exporting-from-a-dll-using-def-files.md).  
  
 Consultez les sections suivantes pour plus d’informations :  
  
-   [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTS](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [LIBRARY](../../build/reference/library.md)  
  
-   [NOM](../../build/reference/name-c-cpp.md)  
  
-   [SECTIONS](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [VERSION](../../build/reference/version-c-cpp.md)  
  
-   [Mots réservés](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence à la génération C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)  