---
title: "/EP (Pr&#233;traiter dans stdout sans directive #line) | Microsoft Docs"
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
  - "/ep"
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EP (option du compilateur C++)"
  - "copier la sortie du préprocesseur dans stdout"
  - "EP (option du compilateur C++)"
  - "-EP (option du compilateur C++)"
  - "sortie du préprocesseur, copier dans stdout"
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /EP (Pr&#233;traiter dans stdout sans directive #line)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prétraite des fichiers source C et C\+\+, puis copie les fichiers prétraités vers le périphérique de sortie standard.  
  
## Syntaxe  
  
```  
/EP  
```  
  
## Notes  
 Au cours de cette opération, toutes les directives du préprocesseur sont exécutées, les expansions de macros sont effectuées et les commentaires sont supprimés.  Pour conserver les commentaires dans la sortie prétraitée, utilisez l'option [\/C \(Conserver les commentaires pendant le prétraitement\)](../../build/reference/c-preserve-comments-during-preprocessing.md) en association avec **\/EP**.  
  
 L'option **\/EP** supprime la compilation.  Vous devez soumettre de nouveau le fichier prétraité en vue de sa compilation.  **\/EP** supprime également les fichiers de sortie des options **\/FA**, **\/Fa** et **\/Fm**.  Pour plus d’informations, consultez [\/FA, \/Fa \(Fichier listing\)](../../build/reference/fa-fa-listing-file.md) et [\/Fm \(Nom de fichier de mappage\)](../../build/reference/fm-name-mapfile.md).  
  
 Les erreurs générées pendant les dernières étapes du traitement désignent les numéros de ligne du fichier prétraité et non pas ceux du fichier source d'origine.  Si vous voulez que les numéros de ligne fassent référence au fichier source d'origine, utilisez plutôt [\/E \(Prétraiter dans stdout\)](../../build/reference/e-preprocess-to-stdout.md).  L'option **\/E** ajoute alors les directives `#line` dans la sortie.  
  
 Pour envoyer la sortie prétraitée dans un fichier, avec les directives `#line`, utilisez l'option [\/P \(Prétraiter jusqu'à un fichier\)](../../build/reference/p-preprocess-to-a-file.md).  
  
 Pour envoyer la sortie prétraitée dans stdout, avec les directives `#line`, utilisez **\/P** et **\/EP** ensemble.  
  
 Vous ne pouvez pas utiliser des en\-têtes précompilés avec l'option **\/EP**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Préprocesseur**.  
  
4.  Modifiez la propriété **Génération du fichier prétraité**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## Exemple  
 La ligne de commande suivante prétraite le fichier `ADD.C`, conserve les commentaires et affiche le résultat sur le périphérique de sortie standard :  
  
```  
CL /EP /C ADD.C  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)