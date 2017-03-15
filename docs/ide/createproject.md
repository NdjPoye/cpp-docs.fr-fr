---
title: "CreateProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateProject (méthode)"
ms.assetid: b5598b46-fe29-4ad0-8bfe-a4dc789aeebd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CreateProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un projet C\+\+.  
  
## Syntaxe  
  
```  
  
      function CreateProject(   
   strProjectName,   
   strProjectPath    
);  
```  
  
#### Paramètres  
 `strProjectName`  
 Chaîne contenant le nom du projet.  
  
 *strProjectPath*  
 Chaîne contenant le chemin d'accès du projet.  
  
## Valeur de retour  
 Objet du projet.  
  
## Notes  
 Appelez cette fonction pour créer un projet C\+\+ que vous pouvez ouvrir dans Visual Studio.  Si le paramètre contextuel **WizardType** de l'Assistant est spécifié en tant que **vsWizardAddSubProject**, le projet est ajouté en tant que sous\-projet au projet existant.  Pour plus d'informations, consultez [ContextParams Enum](../Topic/Context%20Parameters%20for%20Launching%20Wizards.md).  
  
## Exemple  
 Consultez l'option [AddFilesToProject](../ide/addfilestoproject.md).  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)