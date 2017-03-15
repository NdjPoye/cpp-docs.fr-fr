---
title: "/GL (Optimisation de l&#39;ensemble du programme) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gl"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GL (option du compilateur C++)"
  - "GL (option du compilateur C++)"
  - "-GL (option du compilateur C++)"
  - "optimisation de l'ensemble du programme et compilateur C++"
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /GL (Optimisation de l&#39;ensemble du programme)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active l'optimisation de l'ensemble du programme.  
  
## Syntaxe  
  
```  
/GL[-]  
```  
  
## Notes  
 L'optimisation de l'ensemble du programme permet au compilateur de réaliser des optimisations avec des informations sur tous les modules dans le programme.  Sans l'optimisation de l'ensemble du programme, les optimisations sont effectuées par module \(compiland\).  
  
 L'optimisation de l'ensemble du programme étant désactivée par défaut, il faut l'activer de façon explicite.  Toutefois, il est également possible de la désactiver explicitement à l'aide du commutateur **\/GL\-**.  
  
 Avec des informations sur tous les modules, le compilateur peut :  
  
-   Optimiser l'utilisation de registres au\-delà des limites des fonctions.  
  
-   Effectuer un meilleur travail de suivi des modifications apportées aux données globales, autorisant ainsi une réduction du nombre de charges et de magasins.  
  
-   Effectuer un meilleur travail de suivi du jeu d'éléments susceptible d'être modifié par un pointeur déréférencé, réduisant ainsi le nombre de charges et de magasins.  
  
-   Traiter inline une fonction dans un modèle même quand celle\-ci est définie dans un autre module.  
  
 Les fichiers .obj produits avec **\/GL** ne seront pas disponibles pour des utilitaires d'édition des liens, tels que [EDITBIN](../../build/reference/editbin-reference.md) et [DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
 Si vous compilez votre programme avec **\/GL** et [\/c](../../build/reference/c-compile-without-linking.md), vous devez utiliser l'option de l'éditeur de liens \/LTCG pour créer le fichier de sortie.  
  
 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) ne peut pas être utilisé avec **\/GL**  
  
 Le format des fichiers produits avec **\/GL** dans la version actuelle peut ne pas être compatible avec les versions ultérieures de Visual C\+\+.  Vous ne devez pas fournir un fichier .lib composé de fichiers .obj qui ont été produits avec **\/GL** sauf si vous souhaitez livrer des copies du fichier .lib pour toutes les versions de Visual C\+\+ que les utilisateurs sont susceptibles d'utiliser, aujourd'hui et demain.  
  
 Les fichiers .obj produits avec **\/GL** et les fichiers d'en\-tête précompilés ne doivent pas être utilisés pour générer un fichier .lib, sauf si le fichier .lib sera lié sur le même ordinateur ayant servi à la génération du fichier .obj de **\/GL**.  Les informations provenant du fichier d'en\-tête précompilé du fichier .obj seront nécessaires au moment de l'édition des liens.  
  
 Pour plus d'informations sur les optimisations disponibles avec les limites de l'optimisation de programmes complets, consultez [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  **\/GL** permet également l'optimisation guidée par profil ; consultez \/LTCG.  Si, lors de la compilation d'optimisations guidées par profil, vous souhaitez classer les fonctions de vos optimisations guidées par profil, vous devez compiler avec [\/Gy](../../build/reference/gy-enable-function-level-linking.md) ou avec une option du compilateur qui implique \/Gy.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Pour plus d'informations sur **\/GL** dans l'environnement de développement, consultez [\/LTCG \(Génération de code durant l'édition de liens\)](../../build/reference/ltcg-link-time-code-generation.md).  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)