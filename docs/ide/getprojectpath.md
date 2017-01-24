---
title: "GetProjectPath | Microsoft Docs"
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
  - "GetProjectPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProjectPath (méthode)"
ms.assetid: a5e51fe4-c068-47b7-9f2f-1a1d6c71a963
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetProjectPath
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne le chemin d'accès du répertoire du projet.  
  
## Syntaxe  
  
```  
  
      function GetProjectPath(   
   oProj    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
## Valeur de retour  
 Retourne le chemin d'accès du répertoire du projet.  
  
## Notes  
 Appelez cette fonction pour obtenir le chemin d'accès du projet.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [GetProjectFile](../ide/getprojectfile.md)