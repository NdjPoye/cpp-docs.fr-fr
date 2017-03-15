---
title: "/Gm (Activer la r&#233;g&#233;n&#233;ration minimale) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.MinimalRebuild"
  - "/Gm"
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.MinimalRebuild"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gm (option du compilateur C++)"
  - "activer la régénération minimale (option du compilateur C++)"
  - "Gm (option du compilateur C++)"
  - "-Gm (option du compilateur C++)"
  - "régénération minimale"
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Gm (Activer la r&#233;g&#233;n&#233;ration minimale)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet une régénération minimale, qui détermine si les fichiers sources C\+\+ qui incluent des définitions de classe C\+\+ modifiées \(stockées dans des fichiers d'en\-tête \(.h\)\) doivent être recompilés.  
  
## Syntaxe  
  
```  
/Gm  
```  
  
## Notes  
 Le compilateur stocke des informations sur les dépendances entre les fichiers sources et les définitions de classe dans le fichier .idb du projet au cours de la première compilation.  \(Les informations sur les dépendances indiquent quel fichier source est dépendant de quelle définition de classe, et dans quel fichier .h la définition se trouve.\) Les compilations suivantes utilisent les informations stockées dans le fichier .idb pour déterminer si un fichier source a besoin d'être compilé, même s'il inclut un fichier .h modifié.  
  
> [!NOTE]
>  Une régénération minimale s'appuie sur des définitions de classe qui ne changent pas entre les fichiers Include.  Les définitions de classe doivent être globales pour un projet \(il doit exister une seule définition d'une classe donnée\), car les informations sur les dépendances dans le fichier .idb sont créées pour le projet entier.  Si vous possédez plusieurs définitions pour une classe dans votre projet, désactivez la régénération minimale.  
  
 L'éditeur de liens incrémentiels ne prenant pas en charge les métadonnées Windows incluses dans les fichiers .obj à l'aide de l'option [\/ZW \(compilation Windows Runtime\)](../../build/reference/zw-windows-runtime-compilation.md), l'option **\/Gm** est incompatible avec **\/ZW**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Activation de la régénération minimale**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)