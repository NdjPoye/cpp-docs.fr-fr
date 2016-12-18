---
title: "/PDB (Utiliser la base de donn&#233;es du programme) | Microsoft Docs"
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
  - "/pdb"
  - "VC.Project.VCLinkerTool.ProgramDatabaseFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pdb, créer"
  - "/PDB (option de l'éditeur de liens)"
  - "fichiers PDB, créer"
  - "PDB (option de l'éditeur de liens)"
  - "-PDB (option de l'éditeur de liens)"
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDB (Utiliser la base de donn&#233;es du programme)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDB:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 désigne le nom spécifié par l'utilisateur de la base de données du programme \(PDB, program database\) que l'éditeur de liens crée.  Il remplace le nom par défaut.  
  
## Notes  
 Par défaut, lorsque l'option [\/DEBUG](../../build/reference/debug-generate-debug-info.md) est spécifiée, l'éditeur de liens crée une base de données du programme qui stocke les informations de débogage.  Le nom de fichier par défaut de cette base de données est constitué du nom de base du programme suivi de l'extension .pdb.  
  
 Utilisez \/PDB:*filename* pour spécifier le nom du fichier PDB.  En l'absence de \/DEBUG, l'option \/PDB est ignorée.  
  
 Un fichier PDB est limité à 2 Go.  
  
 Pour plus d'informations, consultez [Fichiers .pdb en tant qu'entrée dans l'éditeur de liens](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Déboguer**.  
  
4.  Modifiez la propriété **Génération d'un fichier de base de données du programme**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)