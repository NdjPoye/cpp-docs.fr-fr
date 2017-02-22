---
title: "/OUT (Nom du fichier de sortie) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OutputFile"
  - "/out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OUT (option de l'éditeur de liens C++)"
  - "éditeur de liens (C++), fichiers de sortie"
  - "OUT (option de l'éditeur de liens)"
  - "-OUT (option de l'éditeur de liens)"
  - "fichiers de sortie, nom (option de l'éditeur de liens)"
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /OUT (Nom du fichier de sortie)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/OUT:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 désigne le nom spécifié par l'utilisateur du fichier de sortie.  Il remplace le nom par défaut.  
  
## Notes  
 L'option \/OUT substitue le nom et l'emplacement par défaut du programme créé par l'Éditeur de liens.  
  
 Par défaut, l'éditeur de liens compose le nom du fichier en utilisant le nom de base du premier fichier .obj spécifié et l'extension appropriée \(.exe ou .dll\).  
  
 Cette option est le nom de base par défaut d'un fichier de mappage ou d'une bibliothèque d'importation.  Pour plus d'informations, consultez [Générer fichier de mappage](../../build/reference/map-generate-mapfile.md) \(\/MAP\) et [\/IMPLIB](../../build/reference/implib-name-import-library.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Fichier de sortie**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)