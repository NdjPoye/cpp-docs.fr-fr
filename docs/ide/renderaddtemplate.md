---
title: "RenderAddTemplate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RenderAddTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RenderAddTemplate (méthode)"
ms.assetid: 84c898d6-8676-4ae1-9245-c023e1c9ab92
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# RenderAddTemplate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Affiche un fichier modèle et l'ajoute en option au projet.  
  
## Syntaxe  
  
```  
  
      function RenderAddTemplate(   
   strTemplateFile,   
   strProjectFile,   
   ProjToAddTo,   
   bOpen    
);  
```  
  
#### Paramètres  
 *strTemplateFile*  
 Nom du fichier modèle uniquement, sans le chemin d'accès, relatif à TEMPLATES\_PATH.  
  
 *strProjectFile*  
 Nom du nouveau fichier créé.  Cette chaîne peut inclure le chemin d'accès relatif à PROJECT\_PATH.  
  
 *ProjToAddTo*  
 Objet du projet.  Spécifie le nom du projet si le fichier créé doit être ajouté au projet ; sinon, ignore ou passe **false** si vous n'ajoutez pas le fichier au projet.  
  
 *bOpen*  
 Si la valeur est **true**, ouvre le fichier dans l'éditeur par défaut après l'avoir ajouté au projet.  
  
## Notes  
 Appelez cette fonction pour afficher un fichier modèle et l'ajouter en option au projet.  
  
## Exemple  
  
```  
// Declare the project path and the template path.  
var strProjectPath = wizard.FindSymbol("PROJECT_PATH");  
var strTemplatePath = wizard.FindSymbol("TEMPLATES_PATH");  
// Declare the template header and implementation files.  
var strTemplateHeader = wizard.FindSymbol("TEMPLATE_HEADER");  
var strTemplateImpl = wizard.FindSymbol("TEMPLATE_IMPL");  
// Render the template strTemplateHeader and open it in the editor.  
RenderAddTemplate(strTemplateHeader, strHeaderFile, selProj, true);   
// Render the template strTemplateImpl, but do not open it   
// in the editor.  
RenderAddTemplate(strTemplateImpl, strImplFile, selProj, false);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)