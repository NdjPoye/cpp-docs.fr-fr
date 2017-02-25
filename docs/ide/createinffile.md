---
title: "CreateInfFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateInfFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInfFile (méthode)"
ms.assetid: 941ea2ce-db10-428e-b423-8dc2a7e825cf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CreateInfFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée le fichier Templates.inf de l'Assistant.  
  
## Syntaxe  
  
```  
  
function CreateInfFile( );  
  
```  
  
## Valeur de retour  
 Fichier modèle de l'Assistant.  
  
## Notes  
 Appelez cette fonction pour créer le fichier Templates.inf de l'Assistant à partir du fichier Templatesinf.txt, fichier texte temporaire créé d'abord dans le répertoire temporaire à partir des sélections de l'utilisateur.  Le fichier Templates.inf contient la liste des noms de fichiers créés par l'Assistant.  Pour plus d'informations, consultez [Fichier modèle](../ide/template-files.md).  
  
 Si la fonction ne parvient pas à créer le fichier Templatesinf.txt dans le répertoire temporaire, une erreur s'affiche.  
  
## Exemple  
 Consultez l'option [AddFilesToProject](../ide/addfilestoproject.md).  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [AddFilesToProject](../ide/addfilestoproject.md)   
 [SetFilters](../ide/setfilters.md)   
 [AddFilesToProject](../ide/addfilestoproject.md)