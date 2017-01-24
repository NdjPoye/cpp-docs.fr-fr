---
title: "/ZW (compilation Windows Runtime) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.CompileAsWinRT"
  - "/zw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ZW"
  - "/ZW (option du compilateur)"
  - "Windows Runtime (option du compilateur)"
  - "-ZW"
  - "-ZW (option du compilateur)"
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ZW (compilation Windows Runtime)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compile le code source pour prendre en charge [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\) pour la création d'applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  
  
 Quand vous utilisez **\/ZW** pour compiler, spécifiez également toujours **\/EHsc**.  
  
## Syntaxe  
  
```cpp  
/ZW /EHsc /ZW:nostdlib /EHsc  
```  
  
## Arguments  
 nostdlib  
 Indique que Platform.winmd, Windows.Foundation.winmd et les autres fichiers de métadonnées Windows par défaut \(.winmd\) ne sont pas inclus automatiquement dans la compilation.  À la place, vous devez utiliser l'option de compilateur [\/FU \(nommer le fichier \#using forcé\)](../../build/reference/fu-name-forced-hash-using-file.md) pour spécifier explicitement les fichiers de métadonnées Windows.  
  
## Notes  
 Quand vous spécifiez l'option **\/ZW**, le compilateur prend en charge les fonctionnalités suivantes :  
  
-   les fichiers de métadonnées, les espaces de noms, les types de données et les fonctions nécessaires dont votre application a besoin pour s'exécuter dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ;  
  
-   le décompte automatique des références des objets du [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] et le rejet automatique d'un objet quand son décompte de références atteint zéro.  
  
 L'éditeur de liens incrémentiels ne prenant pas en charge les métadonnées Windows incluses dans les fichiers .obj à l'aide de l'option **\/ZW**, l'option [\/Gm \(Activer la régénération minimale\)](../../build/reference/gm-enable-minimal-rebuild.md) est incompatible avec **\/ZW**.  
  
 Pour plus d'informations, voir [Référence du langage Visual C\+\+](../Topic/Visual%20C++%20Language%20Reference%20\(C++-CX\).md).  
  
## Configuration requise  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)