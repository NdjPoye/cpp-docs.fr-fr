---
title: "AddFilesToProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddFilesToProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddFilesToProject (méthode)"
ms.assetid: 3ff11406-bb4a-4eb7-a8df-c655b964ff76
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# AddFilesToProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute au projet tous les fichiers énumérés dans le fichier Templates.inf.  
  
## Syntaxe  
  
```  
  
      function AddFilesToProject(   
   oProj,   
   strProjectName,   
   InfFile    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
 `strProjectName`  
 Nom du projet.  
  
 *InfFile*  
 Fichier objet Templates.inf.  Ce fichier contient une liste des noms de fichiers que l'Assistant crée une fois terminé.  
  
## Notes  
 Appelez cette fonction pour ajouter au projet tous les fichiers répertoriés dans Templates.inf.  À l'aide de cette fonction, vous pouvez ajouter des fichiers modèles, des fichiers de ressources ou des fichiers d'aide.  
  
## Exemple  
  
```  
// Assign the project path and project name.  
var strProjectPath = wizard.FindSymbol("PROJECT_PATH");  
var strProjectName = wizard.FindSymbol("PROJECT_NAME");  
  
// Create the Visual C++ project and call it "MyProj"  
selProj = CreateProject(strProjectName, strProjectPath);  
selProj.Object.Keyword = "MyProj";  
  
// Add common and specific configurations to the project.  
AddCommonConfig(selProj, strProjectName);  
AddSpecificConfig(selProj, strProjectName);  
  
// Set the project filters  
SetFilters(selProj);  
  
// Create the project's Templates.inf file   
var InfFile = CreateInfFile();  
  
// Add the files in Templates.inf to the project.  
AddFilesToProject(selProj, strProjectName, InfFile);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [CreateInfFile](../ide/createinffile.md)   
 [SetCommonPchSettings](../ide/setcommonpchsettings.md)