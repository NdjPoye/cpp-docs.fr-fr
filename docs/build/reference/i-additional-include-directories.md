---
title: "/I (Autres r&#233;pertoires Include) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories"
  - "/I"
  - "VC.Project.VCNMakeTool.IncludeSearchPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/I (option du compilateur C++)"
  - "Autres répertoires Include (option du compilateur)"
  - "I (option du compilateur C++)"
  - "-I (option du compilateur C++)"
  - "répertoires Include, (option du compilateur C++)"
  - "définir des répertoires Include"
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /I (Autres r&#233;pertoires Include)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute un répertoire à la liste des répertoires de recherche des fichiers Include.  
  
## Syntaxe  
  
```  
/I[ ]directory  
```  
  
## Arguments  
 `directory`  
 Répertoire à ajouter à la liste des répertoires de recherche des fichiers Include.  
  
## Notes  
 Pour ajouter plusieurs répertoires, utilisez cette option plus d'une fois.  Les répertoires sont explorés uniquement jusqu'à ce que le fichier Include spécifié soit trouvé.  
  
 Vous pouvez utiliser cette option avec l'option [\/X \(Ignorer les chemins d'accès Include standard\)](../../build/reference/x-ignore-standard-include-paths.md) \(Ignorer les chemins d'accès Include standard\).  
  
 Le compilateur recherche les répertoires dans l'ordre suivant :  
  
1.  Les répertoires contenant le fichier source.  
  
2.  Les répertoires spécifiés avec l'option **\/I**, dans l'ordre où CL les trouve.  
  
3.  Les répertoires spécifiés dans la variable d'environnement **INCLUDE**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Autres répertoires inclus**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.  
  
## Exemple  
 La commande suivante recherche les fichiers Include demandés par MAIN.c dans l'ordre suivant : d'abord dans le répertoire contenant MAIN.c, ensuite dans le répertoire \\INCLUDE, puis dans le répertoire \\MY\\INCLUDE, et enfin dans les répertoires assignés à la variable d'environnement INCLUDE.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)