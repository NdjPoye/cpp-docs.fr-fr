---
title: "/Fd (Nom de fichier PDB) | Microsoft Docs"
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
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName"
  - "VC.Project.VCCLCompilerTool.ProgramDataBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pdb, créer"
  - "/FD (option du compilateur C++)"
  - "FD (option du compilateur C++)"
  - "-FD (option du compilateur C++)"
  - "fichiers PDB, créer"
  - "base de données du programme (option du compilateur C++)"
  - "nom de fichier de base de données de programme (C++)"
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fd (Nom de fichier PDB)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un nom de fichier pour le fichier de base de données du programme \(PDB\) créé par [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
## Syntaxe  
  
```  
/Fdpathname  
```  
  
## Notes  
 Sans **\/Fd**, le nom de fichier PDB prend la valeur VC`x`0.pdb. par défaut, où `x` est la version principale de Visual C\+\+ en cours d'utilisation.  
  
 Si vous spécifiez un nom de chemin d'accès qui n'inclut pas de nom de fichier \(le chemin d'accès se termine par une barre oblique inverse\), le compilateur crée un fichier .pdb nommé VC`x`0.pdb. dans le répertoire spécifié.  
  
 Si vous spécifiez un nom de fichier sans extension, le compilateur utilise .pdb en tant qu'extension.  
  
 Cette option nomme également le fichier d'état \(.idb\) utilisé pour la régénération minimale et la compilation incrémentielle.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Fichiers de sortie**.  
  
4.  Modifiez la propriété **Nom de fichier objet**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.  
  
## Exemple  
 Cette ligne de commande crée un fichier .pdb nommé PROG.pdb et un fichier .idb nommé PROG.idb :  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)