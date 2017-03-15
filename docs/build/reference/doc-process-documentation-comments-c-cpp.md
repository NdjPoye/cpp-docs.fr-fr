---
title: "/doc (Traiter les commentaires de documentation) (C/C++) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "/doc"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/doc (option du compilateur C++)"
  - "commentaires, code C++"
  - "-doc (option du compilateur C++)"
  - "documentation XML, commentaires dans les fichiers sources"
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /doc (Traiter les commentaires de documentation) (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique au compilateur de traiter les commentaires de documentation contenus dans les fichiers de code source et de créer un fichier .xdc pour chaque fichier de code source contenant commentaires de documentation.  
  
## Syntaxe  
  
```  
/doc[name]  
```  
  
## Arguments  
 `name`  
 Nom du fichier .xdc que le compilateur doit créer.  Uniquement valide lorsqu'un fichier .cpp est passé dans la compilation.  
  
## Notes  
 Les fichiers .xdc sont traités dans un fichier .xml avec xdcmake.exe.  Pour plus d'informations, consultez [Référence XDCMake](../../ide/xdcmake-reference.md).  
  
 Vous pouvez ajouter des commentaires de documentation à vos fichiers de code source.  Pour plus d'informations, consultez [Balises recommandées pour commentaires de documentation](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
 **\/doc** n'est pas compatible avec **\/clr:oldSyntax**.  Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Pour utiliser le fichier .xml généré avec la fonctionnalité IntelliSense, donnez au fichier .xml le même nom de fichier que celui de l'assembly que vous voulez prendre en charge et assurez\-vous qu'il se trouve dans le même répertoire que l'assembly.  Lorsque l'assembly est référencé dans le projet Visual Studio, le fichier .xml est également détecté.  Pour plus d’informations, consultez [Utilisation de la fonctionnalité IntelliSense](../Topic/Using%20IntelliSense.md) et [Insertion de commentaires dans le code XML](../Topic/Supplying%20XML%20Code%20Comments.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **C\/C\+\+**.  
  
4.  Sélectionnez la page de propriétés **Fichiers de sortie**.  
  
5.  Modifiez la propriété **Génération de fichiers de documentation XML**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)