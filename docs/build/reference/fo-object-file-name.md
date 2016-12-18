---
title: "/Fo (Nom de fichier objet) | Microsoft Docs"
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
  - "/Fo"
  - "VC.Project.VCCLCompilerTool.ObjectFile"
  - "VC.Project.VCCLWCECompilerTool.ObjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fo (option du compilateur C++)"
  - "Fo (option du compilateur C++)"
  - "-Fo (option du compilateur C++)"
  - "fichiers objets, affecter des noms"
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fo (Nom de fichier objet)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un nom de substitution pour le nom de fichier \(.obj\) ou de répertoire par défaut.  
  
## Syntaxe  
  
```  
/Fopathname  
```  
  
## Notes  
 Si vous n'utilisez pas cette option, le fichier objet utilise le nom de base du fichier source et l'extension .obj.  Vous pouvez utiliser n'importe quel nom ou extension de votre choix, mais la convention recommandée est d'utiliser .obj.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Fichiers de sortie**.  
  
4.  Modifiez la propriété **Nom de fichier objet**.  Dans l'environnement de développement, le fichier objet doit posséder une extension .obj.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.  
  
## Exemple  
 La ligne de commande suivante crée un fichier objet nommé THIS.obj dans un répertoire existant, \\OBJECT, sur le lecteur B.  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)