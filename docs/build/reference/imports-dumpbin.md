---
title: "/IMPORTS (DUMPBIN) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/imports"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPORTS (option Dumpbin)"
  - "IMPORTS (option Dumpbin)"
  - "-IMPORTS (option Dumpbin)"
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /IMPORTS (DUMPBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPORTS[:file]  
```  
  
 Cette option affiche la liste des DLL \(à lien statique et à [chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)\) qui sont importées vers un fichier exécutable ou une DLL et toutes les différentes importations effectuées à partir de chacune de ces DLL.  
  
 La spécification facultative `file` permet de demander l'affichage uniquement des importations de cette DLL.  Par exemple :  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## Notes  
 La sortie affichée par cette option est similaire à la sortie [\/EXPORTS](../../build/reference/dash-exports.md).  
  
 Seule l'option [\/HEADERS](../../build/reference/headers.md) de DUMPBIN est disponible pour les fichiers générés à l'aide de l'option de compilation [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)