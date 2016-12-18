---
title: "/Fm (Nom de fichier de mappage) | Microsoft Docs"
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
  - "/fm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fm (option du compilateur C++)"
  - "fichiers (C++), créer un fichier de mappage"
  - "Fm (option du compilateur C++)"
  - "-Fm (option du compilateur C++)"
  - "fichiers de mappage (C++), créer avec l'éditeur de liens"
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fm (Nom de fichier de mappage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique à l'éditeur de liens de générer un fichier de mappage contenant une liste de segments dans l'ordre de leur apparition dans le fichier .exe ou DLL correspondant.  
  
## Syntaxe  
  
```  
/Fmpathname  
```  
  
## Notes  
 Par défaut, le fichier de mappage reçoit le nom de base du fichier source C ou C\+\+ correspondant avec une extension .MAP.  
  
 **\/Fm** a le même effet que si vous aviez spécifié l'option de l'éditeur de liens [\/MAP \(Générer fichier de mappage\)](../../build/reference/map-generate-mapfile.md).  
  
 Si vous spécifiez [\/c \(Compiler sans liaison\)](../../build/reference/c-compile-without-linking.md) pour supprimer la liaison, **\/Fm** reste sans effet.  
  
 Dans un fichier de mappage, les symboles globaux se caractérisent généralement par un ou plusieurs traits de soulignement à gauche, car le compilateur ajoute un trait de soulignement à gauche aux noms des variables.  De nombreux symboles globaux qui apparaissent dans le fichier de mappage sont utilisés en interne par le compilateur et les bibliothèques standard.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)