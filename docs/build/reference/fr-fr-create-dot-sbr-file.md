---
title: "/FR, /Fr (Cr&#233;er un fichier .sbr) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.BrowseInformation"
  - "VC.Project.VCCLCompilerTool.BrowseInformation"
  - "/fr"
  - "VC.Project.VCCLCompilerTool.BrowseInformationFile"
  - "VC.Project.VCCLWCECompilerTool.BrowseInformationFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FR (option du compilateur C++)"
  - "FR (option du compilateur C++)"
  - "-FR (option du compilateur C++)"
  - "informations du navigateur sur les symboles"
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FR, /Fr (Cr&#233;er un fichier .sbr)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée des fichiers .sbr.  
  
## Syntaxe  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## Notes  
 Pendant le processus de build, Microsoft Browse Information File Maintenance Utility \(BSCMAKE\) utilise ces fichiers pour créer un fichier .BSC, qui affiche des informations de consultation.  
  
 **\/FR** crée un fichier .sbr contenant des informations symboliques complètes.  
  
 **\/Fr** crée un fichier .sbr qui ne contient pas d’informations sur les variables locales.  
  
 Si vous ne spécifiez pas `filename`, le fichier .sbr a le même nom de base que le fichier source.  
  
 **\/Fr** est déconseillé. Utilisez **\/FR** à la place. Pour plus d’informations, consultez la section « Options du compilateur déconseillées et supprimées » dans [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md).  
  
> [!NOTE]
>  Ne modifiez pas l’extension .sbr. Avec BSCMAKE, les fichiers intermédiaires doivent avoir cette extension.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Dans le volet de navigation, accédez à la page de propriétés **C\/C\+\+**, **Informations de consultation**.  
  
3.  Modifiez la propriété **Fichier d’informations de consultation** ou **Activer les informations de consultation**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)