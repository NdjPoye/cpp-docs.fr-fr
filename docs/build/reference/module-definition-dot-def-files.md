---
title: "Fichiers de d&#233;finition de module (.Def) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .def"
  - "fichiers def"
  - "fichiers de définition de module"
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers de d&#233;finition de module (.Def)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les fichiers de définition de module \(.def\) fournissent à l'éditeur de liens des informations sur les exportations et les attributs ainsi que d'autres données concernant le programme devant être lié.  Un fichier .def est surtout utile lors de la génération d'une DLL.  Dans la mesure où des [options de l'éditeur de liens](../../build/reference/linker-options.md) peuvent remplacer des instructions de définition de module, les fichiers .def ne sont généralement pas nécessaires.  Vous pouvez également utiliser [\_\_declspec\(dllexport\)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) pour spécifier des fonctions exportées.  
  
 Vous pouvez appeler un fichier .def pendant la phase d'exécution de l'éditeur de liens à l'aide de l'option [\/DEF \(spécification du fichier de définition de module\)](../../build/reference/def-specify-module-definition-file.md) de l'éditeur de liens.  
  
 Si vous générez un fichier .exe dépourvu d'exportations, l'utilisation d'un fichier .def a pour effet d'augmenter la taille du fichier de sortie et de ralentir le chargement.  
  
 Pour obtenir un exemple, consultez [Exportation à partir d'une DLL à l'aide de fichiers DEF](../../build/exporting-from-a-dll-using-def-files.md).  
  
 Pour plus d'informations, consultez les sections suivantes :  
  
-   [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTS](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [LIBRARY](../../build/reference/library.md)  
  
-   [NOM](../../build/reference/name-c-cpp.md)  
  
-   [SECTIONS](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [VERSION](../../build/reference/version-c-cpp.md)  
  
-   [Mots réservés](../../build/reference/reserved-words.md)  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [Frequently Asked Questions on Building](http://msdn.microsoft.com/fr-fr/56a3bb8f-0181-4989-bab4-a07ba950ab08)