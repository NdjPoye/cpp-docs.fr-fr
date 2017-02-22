---
title: "/P (Pr&#233;traiter jusqu&#39;&#224; un fichier) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFile"
  - "/p"
  - "VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/P (option du compilateur C++)"
  - "fichiers de sortie, préprocesseur"
  - "P (option du compilateur C++)"
  - "-P (option du compilateur C++)"
  - "prétraiter les fichiers de sortie"
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /P (Pr&#233;traiter jusqu&#39;&#224; un fichier)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prétraite les fichiers sources C et C\+\+, puis écrit la sortie prétraitée dans un fichier.  
  
## Syntaxe  
  
```  
/P  
```  
  
## Notes  
 Le fichier a le même nom de base que le fichier source et une extension .i.  Au cours de cette opération, toutes les directives du préprocesseur sont exécutées, les expansions de macros sont effectuées et les commentaires sont supprimés.  Pour conserver les commentaires dans la sortie prétraitée, utilisez l'option [\/C \(Conserver les commentaires pendant le prétraitement\)](../../build/reference/c-preserve-comments-during-preprocessing.md) en association avec **\/P**.  
  
 **\/P** ajoute des directives `#line` dans la sortie, au début et à la fin de chaque fichier inclus et autour des lignes supprimées par les directives du préprocesseur pour une compilation conditionnelle.  Ces directives renumérotent les lignes du fichier prétraité.  Résultat : les erreurs générées pendant les phases ultérieures du traitement désignent les numéros de ligne du fichier source d'origine et non pas les lignes du fichier prétraité.  Pour supprimer la génération des directives `#line`, utilisez [\/EP \(Prétraiter dans stdout sans directive \#line\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) ainsi que **\/P**.  
  
 L'option **\/P** supprime la compilation.  Elle ne produit pas un fichier .obj, même si vous utilisez [\/Fo \(Nom de fichier objet\)](../../build/reference/fo-object-file-name.md).  Vous devez soumettre de nouveau le fichier prétraité en vue de sa compilation.  **\/P** supprime également les fichiers de sortie des options **\/FA**, **\/Fa** et **\/Fm**.  Pour plus d’informations, consultez [\/FA, \/Fa \(Fichier listing\)](../../build/reference/fa-fa-listing-file.md) et [\/Fm \(Nom de fichier de mappage\)](../../build/reference/fm-name-mapfile.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Préprocesseur**.  
  
4.  Modifiez la propriété **Génération du fichier prétraité**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## Exemple  
 La ligne de commande suivante prétraite `ADD.C`, conserve les commentaires, ajoute les directives `#line` et copie le résultat dans un fichier `ADD.I` :  
  
```  
CL /P /C ADD.C  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\/Fi \(prétraiter le nom du fichier de sortie\)](../../build/reference/fi-preprocess-output-file-name.md)