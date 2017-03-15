---
title: "/FI (Nom du fichier Include impos&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.ForcedIncludes"
  - "VC.Project.VCCLCompilerTool.ForcedIncludeFiles"
  - "VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles"
  - "/fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FI (option du compilateur C++)"
  - "FI (option du compilateur C++)"
  - "-FI (option du compilateur C++)"
  - "prétraitement des fichiers d'en-tête (option du compilateur C++)"
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /FI (Nom du fichier Include impos&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Demande au préprocesseur de traiter le fichier d'en\-tête spécifié.  
  
## Syntaxe  
  
```  
/FI[ ]pathname  
```  
  
## Notes  
 Cette option a le même effet que la spécification du fichier avec des guillemets doubles dans une directive `#include` à la première ligne de chaque fichier source indiqué sur la ligne de commande, dans la variable d'environnement CL, ou dans un fichier de commandes.  Si vous utilisez plusieurs options **\/FI**, les fichiers sont inclus dans l'ordre où ils sont traités par CL.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Fichiers Include forcés**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)